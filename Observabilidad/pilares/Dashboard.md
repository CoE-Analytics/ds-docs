# Dashboard

Un dashboard conecta múltiples fuentes de datos, lo que permite la creación de representaciones visuales de información que de otro modo sería difícil de entender. Se puede utilizar para:

- Mostrar tendencias
- Identificar patrones (usuario, uso, búsqueda, etc.)
- Medir la eficiencia fácilmente
- Identificar datos atípicos y correlaciones
- Ver el estado de salud o el rendimiento del sistema
- Dar una perspectiva del KPI que es importante para un negocio/proceso

## Mejores prácticas

Las preguntas comunes que debe hacerse al crear un dashboard serían:

- ¿Dónde pasó el usuario la mayor parte de su tiempo?
- ¿Qué busca el usuario?
- ¿Cómo puedo ayudar mejor a mi equipo con alertas y resolución de problemas?
- ¿Está mi sistema en buen estado durante el último día/semana/mes/trimestre?

A continuación se detallan los principios a considerar al crear dashboards:

1. Separe un dashboard en varias secciones para simplificar. Agregar salto de página o ancla (#sección) también es una ventaja, si corresponde.
2. Agregue gráficos múltiples y simples. Cree un gráfico simple, tenga más de ellos en lugar de un gráfico complicado, todo en uno.
3. Identificar objetivos o medición de KPI. Identificar objetivos o KPI ayuda a definir lo que se debe lograr.
4. Haga preguntas que puedan ayudar a alcanzar el objetivo o KPI definido. Preguntas como la ubicación, el proveedor de servicios de Internet y la hora del día en que los usuarios realizan solicitudes al servidor serían un buen comienzo.
5. Validar las preguntas. Esto a menudo se hace con partes interesadas, patrocinadores, líderes o gerentes de proyecto.
6. Observe el dashboard que está construido. ¿Reflejan los datos lo que las partes interesadas se propusieron responder?
7. Recuerde siempre que este proceso lleva tiempo. Crear un dashboard es fácil, pero crear un dashboard observable para mostrar patrones es difícil.

## Herramientas recomendadas

| Herramienta               | Ventajas                                                     | Usos recomendados                                            |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Azure Workbooks**       | Plataforma nativa de paneles de Azure                        | Se usa como herramienta para que los equipos técnicos y de ingeniería visualicen e investiguen escenarios |
|                           | Actualización automática                                     | Se usa como herramienta de información para desarrolladores de aplicaciones, ingenieros cloud y otro personal técnico |
|                           | Plantillas e informes GitHub públicos y listos para usar     |                                                              |
|                           | Los parámetros permiten actualizaciones dinámicas en tiempo real |                                                              |
|                           | Puede proporcionar resúmenes de alto nivel que le permitan seleccionar cualquier elemento para obtener datos más exhaustivos usando el valor seleccionado en la consulta |                                                              |
|                           | Puede consultar más orígenes que otras visualizaciones       |                                                              |
|                           | Totalmente personalizable                                    |                                                              |
|                           | Diseñado para la colaboración y la solución de problemas     |                                                              |
| **Azure Dashboards**      | Plataforma nativa de paneles de Azure                        | Entornos exclusivos de Azure/Arc                             |
|                           | Sin costo agregado                                           |                                                              |
|                           | Admite implementaciones a escala                             |                                                              |
|                           | Puede combinar un gráfico de métricas y los resultados de una consulta de log con datos operativos de servicios relacionados |                                                              |
|                           | Permite compartir un dashboard con los propietarios de servicios mediante la integración con RBAC de Azure |                                                              |
| **Azure Managed Grafana** | Visualizaciones de panel único multiplataforma y multinube   | Para los usuarios sin acceso a Azure                         |
|                           | Perfecta integración con Azure                               | Se usa para experiencias de visualización externas, especialmente para dashboards de tipo RAG en entornos SOC y NOC |
|                           | Puede combinar datos de series temporales y eventos en un único panel | Supervisión de CNCF nativa en la nube                        |
|                           | Puede crear dashboards dinámicos basados en la selección de variables por parte del usuario | Entornos multinube                                           |
|                           | Compatibilidad con Prometheus                                | Informes generales de estado, arriba/abajo y tendencias de alto nivel para usuarios de nivel ejecutivo o de administración |
|                           | Se integra con herramientas de supervisión de terceros       | Se usa para mostrar el estado de los entornos, las aplicaciones, la seguridad y la red para una visualización continua en los dashboards de Network Operations Center (NOC) |
|                           | Complementos listos para usarse de la mayoría de las plataformas y herramientas de supervisión |                                                              |
|                           | Plantillas de dashboard centradas en las operaciones         |                                                              |
|                           | Puede crear un dashboard a partir de una plantilla creada y respaldada por la comunidad |                                                              |
|                           | Puede crear un escenario de continuidad empresarial y de desastres que sea independiente del proveedor |                                                              |
| **Power BI**              | Visualizaciones enriquecidas                                 | Se usa para visualizaciones externas dirigidas a niveles ejecutivos y de administración |
|                           | Admite análisis de BI con una amplia segmentación y desglose | Se usa para ayudar a diseñar dashboards de KPI centrados en el negocio para las tendencias a largo plazo |
|                           | Integra datos de varios orígenes                             |                                                              |
|                           | Resultados almacenados en caché para un mejor rendimiento    |                                                              |
|                           | Amplia interactividad                                        |                                                              |
|                           | Compartir fácilmente en toda su organización                 |                                                              |
