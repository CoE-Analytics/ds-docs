# Observabilidad para Azure Databricks

Azure Databricks es un servicio de análisis basado en Apache Spark que facilita el desarrollo e implementación rápidos de análisis de big data.

Spark está diseñado para ejecutarse en un clúster. Puede escalar horizontalmente con cargas de trabajo más grandes que necesitan más máquinas virtuales. Azure Databricks puede escalar horizontal y verticalmente según sea necesario.

## Enfoques para la observabilidad

### Azure Diagnostic Logs

Azure Databricks proporciona [Azure Diagnostic Logging](https://learn.microsoft.com/en-us/azure/databricks/administration-guide/account-settings/audit-logs) listo para usar, lo que proporciona visibilidad de las acciones realizadas en DBFS, Clústeres, Cuentas, Jobs, Notebooks, SSH, Workspace, Secrets, Permisos SQL y Pools de Instancias.

Estos logs se habilitan mediante Azure Portal o CLI y se pueden configurar para que se entreguen a uno de estos recursos de Azure.

- Log Analytics Workspace

- Blob Storage
- Event Hub

### Cluster Event Logs

[Cluster Event Logs](https://learn.microsoft.com/en-us/azure/databricks/compute/configure#cluster-log-delivery) brindan una descripción general rápida de los eventos importantes del ciclo de vida del clúster. El log está estructurado: Timestamp, tipo de evento y detalles. Lamentablemente, no existe una forma nativa de exportar logs a Log Analytics.

### VM Performance Metrics (OMS)

[Log Analytics Agent](https://learn.microsoft.com/en-us/azure/virtual-machines/extensions/oms-linux) proporciona información sobre los contadores de rendimiento de las máquinas virtuales del clúster y ayuda a comprender los patrones de utilización del clúster. Aprovechar el agente OMX de Linux para incorporar máquinas virtuales en Log Analytics ayuda a proporcionar información sobre las métricas de las máquinas virtuales, el rendimiento, el inventario y las métricas de syslog.

### Application Logging

Este es quizás el más importante de todos los logs. La biblioteca
[Spark Monitoring](https://github.com/mspnp/spark-monitoring) recopila métricas sobre el controlador, los ejecutores, JVM, HDFS, cache shuffling, DAG y mucho más. Esta biblioteca proporciona información útil para ajustar los trabajos de Spark.
La biblioteca también incluye dashboards de Grafana listos para usar, que son un excelente punto de partida para crear un dashboard de Azure Databricks.

### Logs a través de API REST

Azure Databricks también proporciona compatibilidad con [REST API](https://docs.databricks.com/api/azure/workspace/introduction). Si se requieren datos de log específicos, estos se pueden recopilar mediante las llamadas a la API REST.

### NSG Flow Logs

Los [logs de flujo del Network security group (NSG)](https://learn.microsoft.com/en-us/azure/network-watcher/network-watcher-nsg-flow-logging-overview) son una característica de Azure Network Watcher que le permite registrar información sobre el tráfico IP que fluye a través de un NSG. Los datos de flujo se envían a cuentas de Azure Storage desde donde puede acceder a ellos y exportarlos a cualquier herramienta de visualización. Estos datos se pueden utilizar para identificar tráfico desconocido o no deseado y monitorear los niveles de tráfico y/o el consumo de ancho de banda.

### Logs de plataforma

Los logs de la plataforma se pueden utilizar para revisar las operaciones de aprovisionamiento/desaprovisionamiento. Esto se puede usar para revisar la actividad en el grupo de recursos administrado de Databricks.
Estos logs se pueden habilitar a través de Azure Monitor > Activity Logs y enviarse a Log Analytics.

### Métricas Ganglia

Las métricas Ganglia son una UI de utilización del clúster y están disponibles en Azure Databricks. Es excelente para ver métricas en vivo de clústeres interactivos. Las métricas de Ganglia están disponibles de forma predeterminada y toman una instantánea del uso cada 15 minutos.
