# Métricas

## Mejores prácticas

### ¿Qué se debe monitorear?

Mediciones críticas del sistema que se relacionan con el estado de la aplicación/máquina, que suelen ser excelentes candidatos para alertas. Pueden incluir:

- Utilización de CPU y memoria.
- Tasa de requests.
- Longitud de la cola.
- Recuento de excepciones inesperadas.
- Métricas de servicio dependientes, como el tiempo de respuesta para la caché de Redis, SQL Server o Service bus.

Medidas importantes relacionadas con el negocio, que impulsan la presentación de informes a las partes interesadas. Algunos ejemplos pueden incluir:

- Jobs realizados.
- Duración de la sesión del usuario.
- Juegos jugados.
- Visitas al sitio.

### Etiquetas de dimensiones

Los sistemas actuales suelen definir una métrica de serie temporal única como la combinación del nombre de la métrica y su diccionario de etiquetas de dimensión. Las etiquetas son una excelente manera de distinguir una instancia de una métrica de otra y, al mismo tiempo, permiten realizar la agregación y otras operaciones en el conjunto para su análisis. Algunas etiquetas comunes utilizadas en las métricas pueden incluir:

- Nombre del contenedor
- Nombre de host
- Versión del código
- Nombre del clúster de Kubernetes
- Región de Azure

## Herramientas recomendadas

- **Azure Monitor**: conjunto de servicios que incluyen métricas del sistema, log analytics y más.
- **Prometheus**: una aplicación de alerta y monitoreo en tiempo real. Su formato de exposición para exponer series temporales es la base del formato estándar de OpenMetrics.
- **Thanos**: configuración de Prometheus de código abierto y alta disponibilidad con capacidades de almacenamiento a largo plazo.
- **Cortex**: Prometheus horizontalmente escalable, de alta disponibilidad, multiinquilino y de largo plazo.
- **Grafana**: dashboard y herramienta de visualización de código abierto. Admite fuentes de datos de logs, métricas y trazas distribuidas.
