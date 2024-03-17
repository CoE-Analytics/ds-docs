# Delta Live Tables

Delta Live Tables es un framework declarativo de ETL para Databricks Data Intelligence Platform que ayuda a los equipos de datos a simplificar el ETL streaming y batch de manera rentable. Simplemente defina las transformaciones que desea realizar en sus datos y permita que los pipelines DLT administren automáticamente la orquestación de tareas, la administración de clústeres, el monitoreo, la calidad de los datos y el manejo de errores.

- Ingestión de datos eficiente
  La construcción de pipelines ETL listos para producción comienza con la ingestión. Con DLT, cargue datos desde cualquier origen de datos compatible con Spark.
  - Utilice Auto Loader y tablas streaming para introducir datos de forma incremental en la capa Bronce.
  - Ingiera desde almacenamiento en la nube, buses de mensajes y sistemas externos
  - Utilice change data capture (CDC) para actualizar tablas en función de los cambios en los datos de origen
- Transformación de datos inteligente y rentable
  A partir de solo unas pocas líneas de código, DLT determina la forma más eficiente de crear y ejecutar sus pipelines, optimizando la relación precio/rendimiento y minimizando la complejidad.
  - Implemente instantáneamente una arquitectura de medallón optimizada con tablas streaming y vistas materializadas.
  - Optimice la calidad de los datos para obtener el máximo valor empresarial con características como las expectations
  - Actualice los pipelines en modo continuo o activado para satisfacer sus necesidades de actualización de datos
- Configuración y mantenimiento sencillos de pipelines
  Los pipelines DLT simplifican el desarrollo de ETL al automatizar prácticamente toda la complejidad operativa inherente. DLT maneja automáticamente:
  - Orquestación de tareas
  - CI/CD y control de versiones
  - Infraestructura informática de escalamiento automático para ahorrar costos
  - Monitoreo a través de métricas en el log de eventos
  - Manejo de errores y recuperación de fallas
- Motor de procesamiento de flujo de próxima generación
  Spark Structured Streaming es la tecnología central que desbloquea pipelines streaming, proporcionando una API unificada para el procesamiento batch y streaming. Los pipelines DLT aprovechan la latencia inherente de menos de un segundo de Spark Structured Streaming y una relación precio/rendimiento récord. Aunque puede crear manualmente sus propios pipelines streaming, los pipelines DLT pueden proporcionar un tiempo de obtención de valor más rápido, una mejor velocidad de desarrollo continuo y un menor costo total de propiedad debido a la sobrecarga operativa que administran automáticamente.
- Gobernanza y almacenamiento de datos unificados
  La ejecución de pipelines DLT en Databricks significa que se beneficiará de los componentes fundamentales de Data Intelligence Platform: Unity Catalog y Delta Lake. Sus datos sin procesar se optimizan con Delta Lake, el único framework de almacenamiento de código abierto diseñado desde cero para datos en streaming y batch. Unity Catalog le brinda una gobernanza integrada y detallada para todos sus datos y activos de IA con un modelo consistente para descubrir, acceder y compartir datos en las nubes. Unity Catalog también brinda soporte nativo para Delta Sharing, el primer protocolo abierto de la industria para compartir datos de manera simple y segura con otras organizaciones.
