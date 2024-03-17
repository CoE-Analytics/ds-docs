# Feature Store

Proporcione a los equipos de datos la capacidad de crear nuevas features, explorar y reutilizar los existentes, publicar features en almacenamiento en línea de baja latencia, crear conjuntos de datos de entrenamiento y recuperar valores de features para inferencia batch.

- Features como activos reutilizables

  Feature Registry proporciona un registro con capacidad de búsqueda de todos los features, su definición asociada, datos de origen y sus consumidores, lo que elimina un trabajo considerable entre los equipos. Los científicos de datos, analistas e ingenieros de ML pueden buscar features basadas en los datos sin procesar consumidos y utilizar features directamente o bifurcar features existentes.

- Features consistentes para entrenamiento y servicio

  Feature Provider ofrece los features en dos modos. El modo batch proporciona features de alto rendimiento para entrenar modelos o inferencia batch. El modo en línea proporciona features de baja latencia para servir modelos de ML o para el consumo en aplicaciones de BI. Los features utilizados en el entrenamiento de modelos se rastrean automáticamente con el modelo y, durante la inferencia, el modelo mismo las recupera directamente del feature store.

- Features seguros con control integrado

  Las integraciones del feature store proporcionan el linaje completo de los datos utilizados para calcular los features. Los features tienen ACL asociadas para garantizar el nivel adecuado de seguridad. La integración con MLflow garantiza que se almacenen junto con los modelos de ML, lo que elimina el drift entre entrenamiento y servicio.
