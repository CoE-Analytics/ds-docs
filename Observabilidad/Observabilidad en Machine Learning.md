# Observabilidad en Machine Learning

El proceso de desarrollo de un sistema de software con componente de ML es más complejo que el del software tradicional. Necesitamos monitorear cambios y variaciones en tres dimensiones: el código, el modelo y los datos. Podemos distinguir dos etapas de la vida útil de dicho sistema: experimentación y producción que requieren diferentes enfoques para la observabilidad, como se analiza a continuación:

## Experimentación y ajuste de modelos

Al desarrollar y ajustar modelos de ML, los científicos de datos están interesados en observar y comparar métricas de rendimiento seleccionadas para varios parámetros del modelo.
Hay muchas soluciones de evaluación de métricas de modelos disponibles, tanto de código abierto, como propietarias
A continuación se puede encontrar una comparación de varias opciones:

|                                      | Azure ML                                                     | MLFlow                                                       | TensorBoard                                                  | Application Insights                                         |
| ------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Soporte de métricas**              | Valores, imágenes, matrices, logs                            | Valores, imágenes, matrices y gráficos                       | Métricas relevantes para la fase de investigación            | Valores, imágenes, matrices, logs                            |
| **Personalizable**                   | Básico                                                       | Básico                                                       | Muy básico                                                   | Alto                                                         |
| **Métricas accesibles**              | Portal AML, SDK AML                                          | MLFlow UI, API de servicio de Tracking                       | UI de tensorboard, objeto histórico                          | Application Insights                                         |
| **Logs accesibles**                  | Logs continuos escritos en archivos .txt en blob storage. No se pueden consultar | Los logs continuos no se almacenan                           | Los logs continuos no se almacenan                           | Application Insights en Azure Portal. Consultable con KQL    |
| **Facilidad de uso y configuración** | Muy sencillo, solo un portal                                 | Más piezas móviles debido al servidor de seguimiento remoto  | Un poco de sobrecarga del proceso. También dependiendo del marco de ML | Se deben mantener más partes móviles ya que es necesario mantener una aplicación personalizada |
| **Compartibilidad**                  | Entre personas con acceso al espacio de trabajo AML          | Entre personas con acceso a un servidor de seguimiento remoto | Entre personas con acceso al mismo directorio                | Entre personas con acceso a AppInsights                      |

## Modelo en producción

El modelo entrenado se puede implementar en producción como contenedor. Puede monitorearlo utilizando métodos de observabilidad de microservicios. MLFLow es una forma alternativa de implementar el modelo ML como servicio.

## Entrenamiento y reentrenamiento

Al volver a entrenar un modelo, puede monitorear la información de cada ejecución, incluidos los resultados, los logs y las métricas

## Performance del modelo a lo largo del tiempo: data drift

En algunos casos el rendimiento del modelo puede degradarse. Esto puede suceder en caso de que los datos cambien drásticamente y ya no muestren los patrones que observamos durante el desarrollo del modelo. Este efecto se llama data drift. Las plataformas como Azure Machine Learning o Azure Databricks realizan automaticamente el monitoreo de data drift.
