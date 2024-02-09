# Observabilidad como código

En la medida de lo posible, la configuración y gestión de los activos de observabilidad, como el aprovisionamiento de recursos, las alertas y los dashboards, deben gestionarse como código, mediante plantillas Terraform / Bicep / ARM.

## Ejemplos de observabilidad como código

- Dashboards como Código: los dashboards se pueden crear como plantillas JSON o XML. Esta plantilla se mantiene con control de versiones y se puede revisar cualquier cambio. Ejemplo: <https://learn.microsoft.com/en-us/azure/azure-portal/azure-portal-dashboards-create-programmatically>

- Alertas como Código: las alertas se pueden crear mediante plantillas Terraform o ARM. Estas alertas pueden versionarse en el repositorio de código e implementarse como parte de canalizaciones DevOps. Ejemplo: <https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/monitor_metric_alert>

- Automatización de consultas de Log Analytics: existen varios casos de uso en los que puede ser necesaria la automatización de consultas de Log Analytics. Por ejemplo, generación automática de informes, ejecución de consultas personalizadas mediante programación para análisis, depuración, etc. Para que estos casos de uso funcionen, las consultas de logs deben estar en un repositorio de código y la automatización se puede crear mediante log analytics REST o Azure CLI.

## Por qué

- Hace que la configuración sea repetible y automatizable. También evita la configuración manual de alertas y dashboards desde cero.
- Los dashboards configurados ayudan a solucionar errores durante la integración y la implementación (CI/CD)
- Podemos auditar los cambios y revertirlos si hay algún problema.
- Identificar conocimientos prácticos a partir de los datos de métricas generados en todos los entornos, no solo en producción.
- La configuración y gestión de activos de observabilidad, como el umbral de alerta, la duración y los valores de configuración mediante IAC, nos ayudan a evitar errores de configuración u omisiones durante la implementación.
- Al practicar la observabilidad como código, el equipo puede revisar los cambios de manera similar a otras contribuciones de código.
