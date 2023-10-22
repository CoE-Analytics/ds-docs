# Prompt Flow

## Inicializar flujo

### Crear desde cero

Se pueden crear tres tipos de flujos:

- standard: Estructura básica de flujo.
- chat: Está diseñado para el desarrollo de aplicaciones conversacionales, basándose en las capacidades del flujo estándar y brindando soporte mejorado para entradas/salidas de chat y administración del historial de chat.
- evaluation: Son tipos especiales de flujos que evalúan qué tan bien se alinean los resultados de un flujo con criterios y objetivos específicos.

```python
# Crear un flujo
pf flow init --flow <flow-name>

# Crear un flujo de chat
pf flow init --flow <flow-name> --type chat
```

Estructura de la carpeta de flujo:

- **flow.dag.yaml**: la definición de flujo con entradas/salidas, nodos, herramientas y variantes.
- **.promptflow/flow.tools.json**: contiene todos los metadatos de herramientas del paquete a los que se hace referencia en flow.dag.yaml.
- **Archivos de código fuente (.py, .jinja2)**: administrados por el usuario, los scripts de código a los que hace referencia las herramientas.
- **requirements.txt**: dependencias para este flujo.

### Crear a partir de código existente

Se puede generar las definiciones de yaml necesarias para el flujo de prompt desde la carpeta existente, utilizando script de herramientas y plantillas de prompt.

