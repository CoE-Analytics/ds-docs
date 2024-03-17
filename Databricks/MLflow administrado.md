# MLflow administrado

Managed MLflow amplía la funcionalidad de MLflow, una plataforma de código abierto desarrollada por Databricks para la gestión del ciclo de vida de machine learning, centrándose en la confiabilidad, seguridad y escalabilidad empresarial. La última actualización de MLflow presenta características innovadoras de LLMOps que mejoran su capacidad para administrar e implementar modelos LLM. Este soporte ampliado de LLM se logra a través de nuevas integraciones con herramientas LLM estándar de la industria, Hugging Face Transformers y funciones OpenAI, así como MLflow AI Gateway. Además, la integración de MLflow con LangChain y Prompt Engineering UI permite el desarrollo de modelos simplificados para crear aplicaciones generativas de IA para una variedad de casos de uso, incluidos chatbots, resumen de documentos, clasificación de texto, análisis de sentimientos y más.

## Beneficios

- Desarrollo de modelos

  Mejore y acelere la gestión del ciclo de vida de ML con un framework estandarizado para modelos listos para producción. Las recetas MLflow  permiten un arranque fluido de proyectos de ML, una iteración rápida y una implementación de modelos a gran escala. Cree aplicaciones como chatbots, resúmenes de documentos, análisis de sentimientos y clasificación sin esfuerzo. Desarrolle fácilmente aplicaciones generativas de IA con AI Gateway y Prompt Engineering de MLflow, perfectamente integrados con LangChain, Hugging Face y OpenAI.

- Seguimiento de experimentos

  Ejecute experimentos con cualquier biblioteca, framework o lenguaje de ML y realice un seguimiento automático de los parámetros, métricas, códigos y modelos de cada experimento. Al usar MLflow en Databricks, puede compartir, administrar y comparar de forma segura los resultados de los experimentos junto con los artefactos y las versiones de código correspondientes, gracias a las integraciones dentro de Databricks Workspace y notebooks.

- Gestión de modelos

  Utilice un lugar central para descubrir y compartir modelos de ML, colaborar para pasarlos de la experimentación a testing y producción, integrarlos con workflows de aprobación y gobernanza y pipelines de CI/CD, y monitorear los despliegues de ML y su rendimiento. MLflow Model Registry facilita el intercambio de experiencia y conocimientos, y le ayuda a mantener el control.

- Despliegue del modelo

  Implemente rápidamente modelos de producción para inferencia batch en Spark o como API REST mediante la integración con contenedores Docker, Azure ML o Amazon SageMaker. Con Managed MLflow en Databricks, puede poner en funcionamiento y monitorear modelos de producción mediante Databricks Jobs Scheduler y clústeres administrados automáticamente para escalar según las necesidades comerciales.

  Las últimas actualizaciones de MLflow empaquetan perfectamente aplicaciones de IA generativas para su implementación. Ahora puede implementar sus chatbots y otras aplicaciones de IA a escala utilizando Databricks Model Serving.

## Características

MLflow es un conjunto liviano de API e interfaces de usuario que se pueden usar con cualquier framework de ML en todo el flujo de trabajo de Machine Learning. Incluye cuatro componentes: MLflow Tracking, MLflow Projects, MLflow Models y MLflow Model Registry.

### MLflow Tracking

Logee automáticamente parámetros, versiones de código, métricas y artefactos para cada ejecución utilizando Python, REST, R API y Java API.

- Ingeniería prompt: desarrollo de modelos simplificado para crear aplicaciones de IA generativa para una variedad de casos de uso, como chatbots, resumen de documentos, análisis de sentimientos y clasificación con AI Gateway e Prompt Engineering de MLflow respaldados por la integración nativa con LangChain y una interfaz de usuario perfecta y sin código para creación rápida de prototipos e iteraciones.
- MLflow Tracking Server: comience rápidamente con un servidor de seguimiento integrado para registrar todas las ejecuciones y experimentos en un solo lugar. No se necesita configuración en Databricks.
- Gestión de experimentos: cree, proteja, organice, busque y visualice experimentos desde el workspace con control de acceso y consultas de búsqueda.
- Barra lateral de ejecución de MLflow: realice un seguimiento automático de las ejecuciones desde los notebooks y capture una instantánea de su notebooks para cada ejecución, de modo que siempre pueda volver a las versiones anteriores de su código.
- Logging de datos con ejecuciones: logee parámetros, conjuntos de datos, métricas, artefactos y más como ejecuciones en archivos locales, en una base de datos compatible con SQLAlchemy o de forma remota en un servidor de seguimiento.
- Integración de Delta Lake: realice un seguimiento de conjuntos de datos a gran escala que alimentaron sus modelos con instantáneas de Delta Lake.
- Tienda de Artefactos: almacene archivos grandes, como buckets de S3, sistemas de archivos NFS compartidos y modelos en Amazon S3, Azure Blob Storage, Google Cloud Storage, servidor SFTP, NFS y rutas de archivos locales.

### MLflow Models

Un formato estándar para empaquetar modelos de ML que se puede usar en una variedad de herramientas posteriores, por ejemplo, servicio en tiempo real a través de una API REST o inferencia por lotes en Apache Spark.

- Personalización del modelo: utilice modelos Python personalizados para modelos de una biblioteca de ML que no sea compatible explícitamente con los tipos integrados de MLflow.
- Modelos integrados: MLflow proporciona varios tipos estándar que pueden ser útiles en sus aplicaciones, como funciones de Python y R, Hugging Face, OpenAI y LangChain, PyTorch, Spark MLlib, TensorFlow y ONNX.
- Herramientas de despliegue integrada: despliegue rápidamente en Databricks a través de Apache Spark UDF para una máquina local o varios otros entornos de producción, como Microsoft Azure ML, Amazon SageMaker y la creación de imágenes Docker para implementación.

### MLflow Model Registry

Registre los modelos de MLflow en MLflow Model Registry. Un modelo registrado tiene un nombre, versión, etapa y otros metadatos únicos.

- Versionamiento de modelos: realice un seguimiento automático de las versiones de los modelos registrados cuando se actualicen.
- Etapa del modelo: asigne etapas preestablecidas o personalizadas a cada versión del modelo, como "Staging" y "Production" para representar el ciclo de vida de un modelo.
- Integración del workflow CI/CD: registre las transiciones de etapa, solicite, revise y apruebe cambios como parte de los procesos de CI/CD para un mejor control y gobernanza.
- Transiciones de etapa: registre nuevos eventos o cambios como actividades que logean automáticamente usuarios, cambios y metadatos adicionales, como comentarios.

### MLflow AI Gateway

- Gobernar el acceso a LLMs: administra las credenciales de SaaS LLM
- Controlar costos: establecer límites de tarifas
- Estandarizar las interacciones de LLM: experimente con diferentes LLM de OSS/SaaS con interfaces de entrada/salida estándar para diferentes tareas: finalización, chat, embeddings

### MLflow Recipes

- Inicio de proyecto simplificado: MLflow Recipes proporciona componentes conectados listos para usar para crear e implementar modelos de ML.
- Iteración acelerada del modelo: MLflow Recipes crea pasos estandarizados y reutilizables para la iteración del modelo, lo que hace que el proceso sea más rápido y menos costoso.
- Transferencias automatizadas del equipo: la estructura con opinión proporciona código modularizado listo para producción, lo que permite la transferencia automática de la experimentación a la producción.

### MLflow Projects

Los proyectos MLflow le permiten especificar el entorno de software que se utiliza para ejecutar su código. Actualmente, MLflow admite los siguientes entornos de proyecto: entorno Conda, entorno de contenedor Docker y entorno del sistema. Cualquier repositorio de Git o directorio local se puede tratar como un proyecto de MLflow.

- Modo de ejecución remota: ejecute MLflow Projects desde Git o fuentes locales de forma remota en clústeres de Databricks mediante la CLI de Databricks para escalar rápidamente su código.
