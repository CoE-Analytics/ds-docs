# Prompt Flow

## Inicializar flujo

### Crear desde cero

Se pueden crear tres tipos de flujos:

- standard: Estructura básica de flujo.
- chat: Está diseñado para el desarrollo de aplicaciones conversacionales, basándose en las capacidades del flujo estándar y brindando soporte mejorado para entradas/salidas de chat y administración del historial de chat.
- evaluation: Son tipos especiales de flujos que evalúan qué tan bien se alinean los resultados de un flujo con criterios y objetivos específicos.

```bash
# Crear un flujo
pf flow init --flow <flow-name>

# Crear un flujo de chat
pf flow init --flow <flow-name> --type chat
```

Estructura de la carpeta de flujo:

- **flow.dag.yaml**: la definición de flujo con entradas/salidas, nodos, herramientas y variantes.
- **.promptflow/flow.tools.json**: contiene todos los metadatos de herramientas del paquete a los que se hace referencia en `flow.dag.yaml`.
- **Archivos de código fuente (.py, .jinja2)**: administrados por el usuario, los scripts de código a los que hace referencia las herramientas.
- **requirements.txt**: dependencias para este flujo.

### Crear a partir de código existente

Se puede generar las definiciones de yaml necesarias para el flujo de prompt desde la carpeta existente, utilizando script de herramientas y plantillas de prompt.

```bash
# Crear un flujo en una carpeta existente
pf flow init --flow <flow-name> --entry <entry-file-name> --function <tool-function-name> --prompt-template <prompt-tempate>
```

## Testear flujo

### Testeo

1. CLI

   ```bash
   # Testear flujo
   pf flow test --flow <flow-name>

   # Testear flujo con una variante especifica
   pf flow test --flow <flow-name> --variant '${<node-name>.<variant-name>}'
   ```

   ```bash
   # Testear nodo
   pf flow test --flow <flow-name> --node <node-name>
   ```

   ```bash
   # Testear en modo interactivo
   pf flow test --flow <flow-name> --interactive
   ```

2. Python

   ```python
   from promptflow import PFClient

   pf_client = PFClient()

   # Testear flujo
   inputs = {"<flow_input_name>": "<flow_input_value>"}
   flow_result = pf_client.test(flow="<flow_folder_path>", inputs=inputs)
   print(f"Flow outputs: {flow_result}")
   ```

   ```python
   from promptflow import PFClient

   pf_client = PFClient()

   # Testear nodo
   inputs = {<node_input_name>: <node_input_value>}
   node_result = pf_client.test(flow=<flow_folder_path>, inputs=inputs, node=<node_name>)
   print(f"Node outputs: {node_result}")
   ```

Promptflow CLI generará registros de test y resultados en `.promptflow`

### Depuración

Se puede depurar un nodo de Python en VScode mediante la extensión.

## Ejecutar flujo

### Crear una ejecución batch

1. CLI

   Una prueba masiva permite ejecutar el flujo con un conjunto de datos grande y generar resultados para cada fila de datos, y los resultados de la ejecución se registrarán en la base de datos local para que pueda usar comandos pf para ver los resultados de la ejecución en cualquier momento.

   ```bash
   pf run create --flow standard/web-classification --data standard/web-classification/data.jsonl --stream --name my_first_run 
   ```

   Si no se especifica el parámetro `--name`, el nombre de la ejecución se generará en un patrón determinado con un timestamp.
   Con un nombre de ejecución, puede ver o visualizar fácilmente los detalles de la ejecución utilizando los siguientes comandos:

   ```bash
   pf run show-details -n my_first_run
   pf run visualize -n my_first_run
   ```

2. Python

   ```python
   flow = "standard/web-classification"
   data= "standard/web-classification/data.jsonl"

   base_run = pf.run(
       flow=flow,
       data=data,
       stream=True,
   )

   details = pf.get_details(base_run)
   details.head(10)

   pf.visualize(base_run)
   ```

### Evaluar el flujo

Utilizamos el flujo de evaluación-clasificación-precisión para evaluar. Este es un flujo que ilustra cómo evaluar el desempeño de un sistema de clasificación. Implica comparar cada predicción con la verdad y asignar una calificación de Correcto o Incorrecto, y agregar los resultados para producir métricas como la precisión.

1. CLI

   ```bash
   pf run create --flow evaluation/eval-classification-accuracy --data standard/web-classification/data.jsonl --column-mapping groundtruth='${data.answer}' prediction='${run.outputs.category}' --run my_first_run --stream
   ```

   También puedes ver los detalles de la ejecución con:

   ```bash
   pf run stream -n my_first_eval_run
   pf run show-details -n my_first_eval_run
   pf run show-metrics -n my_first_eval_run
   ```

   Puede visualizar las dos ejecuciones al mismo tiempo con el siguiente comando:

   ```bash
   pf run visualize -n "my_first_run,my_first_eval_run"
   ```

2. Python

   ```python
   eval_flow = "evaluation/eval-classification-accuracy"
   data= "standard/web-classification/data.jsonl"

   eval_run = pf.run(
       flow=eval_flow,
       data=data,
       run=base_run,
       column_mapping={
         "groundtruth": "${data.answer}",
         "prediction": "${run.outputs.category}",
       }
   )

   pf.stream(eval_run)

   details = pf.get_details(eval_run)
   details.head(10)

   metrics = pf.get_metrics(eval_run)
   print(json.dumps(metrics, indent=4))

   pf.visualize([base_run, eval_run])
   ```

#### Cómo registrar métricas

Promptflow admite el registro y seguimiento de experimentos mediante la función `log_metric`. Una métrica es un par clave-valor que registra una única medida flotante. En un nodo de Python, puede registrar una métrica con el siguiente código:

```python
from promptflow import log_metric, tool

@tool
def example_log_metrics():
  metric_key = "accuracy"
  metric_value = 1.0
  log_metric(metric_key, metric_value)
```

## Ajustar prompts usando variantes

El concepto de variantes se utiliza para ayudar a ajustar prompts de una manera más eficiente, ayudando a probar el comportamiento del modelo en diferentes condiciones, como diferentes textos, formatos, contexto, temperatura o top-k, comparando y encontrando el mejor prompt y configuración que maximice la precisión, diversidad o coherencia del modelo.

Ejemplo de variante:

```yaml
...
nodes:
- name: summarize_text_content
  use_variants: true
...
node_variants:
  summarize_text_content:
    default_variant_id: variant_0
    variants:
      variant_0:
        node:
          type: llm
          source:
            type: code
            path: summarize_text_content.jinja2
          inputs:
            deployment_name: text-davinci-003
            max_tokens: '128'
            temperature: '0.2'
            text: ${fetch_text_content_from_url.output}
          provider: AzureOpenAI
          connection: open_ai_connection
          api: completion
          module: promptflow.tools.aoai
      variant_1:
        node:
          type: llm
          source:
            type: code
            path: summarize_text_content__variant_1.jinja2
          inputs:
            deployment_name: text-davinci-003
            max_tokens: '256'
            temperature: '0.3'
            text: ${fetch_text_content_from_url.output}
          provider: AzureOpenAI
          connection: open_ai_connection
          api: completion
          module: promptflow.tools.aoai
```

Puede ejecutar una variante de esta forma:

1. CLI

   ```bash
   pf run create --flow web-classification --data web-classification/data.jsonl --variant '${summarize_text_content.variant_1}' --stream --name my_first_variant_run
   ```

2. Python

   ```python
   from promptflow import PFClient

   pf = PFClient()
   flow = "web-classification"
   data= "web-classification/data.jsonl"

   variant_run = pf.run(
       flow=flow,
       data=data,
       variant="${summarize_text_content.variant_1}",
   )

   pf.stream(variant_run)
   ```

## Implementar flujo

### Implementar un flujo usando el servidor de desarrollo

```bash
pf flow serve --source <path-to-your-flow-folder> --port 8080 --host localhost
```

Puede abrir otra terminal para probar el endpoint con el siguiente comando:

```bash
curl http://localhost:8080/score --data '{"url":"https://play.google.com/store/apps/details?id=com.twitter.android"}' -X POST  -H "Content-Type: application/json"
```

También puede probar abriendo un browser en http://localhost:8080

### Implementar un flujo usando Docker

1. Crear un flujo en formato Docker

   ```bash
   pf flow build --source <path-to-your-flow-folder> --output <your-output-dir> --format docker
   ```

   Ejemplo:

   ```bash
   pf flow build --source ../../flows/standard/web-classification --output dist --format docker
   ```

2. Crear imagen Docker

   ```bash
   docker build dist -t web-classification-serve
   ```

3. Ejecutar imagen

   Primero deberá configurar las variables de entorno en el contenedor para que las conexiones funcionen.

   ```bash
   docker run -p 8080:8080 -e OPEN_AI_CONNECTION_API_KEY=<secret-value> web-classification-serve
   ```

4. Testear el endpoint

   ```bash
   curl http://localhost:8080/score --data '{"url":"https://play.google.com/store/apps/details?id=com.twitter.android"}' -X POST  -H "Content-Type: application/json"
   ```
