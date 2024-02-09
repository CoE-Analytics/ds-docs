# Observabilidad de los pipelines de CI/CD

## Beneficios

- Tener la instrumentación adecuada durante el tiempo de construcción ayuda a obtener información sobre las distintas etapas del proceso de construcción y lanzamiento.
- Ayuda a los desarrolladores a comprender dónde están los cuellos de botella en el rendimiento del pipeline.
- Ayuda a identificar tendencias en fallas, lo que permite a los desarrolladores realizar rápidamente análisis de la causa raíz.
- Ayuda a proporcionar una visión de toda la organización sobre el estado del pipeline para identificar fácilmente las tendencias.

## Puntos a considerar

- Es importante identificar los indicadores clave de rendimiento (KPI) para evaluar un proceso de CI/CD exitoso.
- Dependiendo de las herramientas utilizadas (Azure DevOps, Jenkins, etc.), los informes básicos sobre los pipelines están disponibles de forma inmediata. Es importante evaluar estos informes con respecto a los KPI para comprender si se necesita una solución de informes personalizada para sus procesos.

## Informes de Azure DevOps Pipelines con Power BI

El [Azure DevOps Pipelines Report](https://github.com/Azure-Samples/powerbi-pipeline-report) contiene una plantilla de Power BI para supervisar datos de proyectos, canalizaciones y ejecución de canalizaciones de una organización de Azure DevOps.
Esta tablero proporciona observabilidad para los pipelines CI/CD al mostrar varias métricas, como tiempo de ejecución promedio, estadísticas de resultados de ejecución, etc. en una tabla. Además, la segunda página de la plantilla visualiza las tendencias de éxito y error de la canalización mediante gráficos de Power BI.
