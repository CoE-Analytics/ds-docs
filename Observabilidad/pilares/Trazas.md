# Trazas

## Mejores prácticas

- Asegúrese de que se rastree al menos las transacciones clave.
- Incluya en cada traza la información necesaria para identificar las versiones de software. Esto es importante para correlacionar las implementaciones y la degradación del sistema.
- Asegúrese de que las dependencias estén incluidas en el seguimiento (bases de datos, E/S).
- Si los costos son una preocupación, utilice el muestreo, evitando descartar errores, comportamientos inesperados e información crítica.
- No reinvente la rueda, utilice las herramientas existentes para recopilar y analizar los datos.
- Asegúrese de que se sigan las políticas y restricciones de información de identificación personal.

## Herramientas recomendadas

- **Azure Monitor**: conjunto de servicios que incluyen métricas del sistema, log analytics y más.
- **Jaeger Tracing**: rastreo distribuido de extremo a extremo de código abierto.
- **Grafana**: dashboard y herramienta de visualización de código abierto. Admite fuentes de datos de logs, métricas y trazas distribuidas.

Considere el uso de OpenTelemetry, ya que implementa la propagación de contexto multiplataforma de código abierto para transacciones distribuidas de un extremo a otro a través de componentes heterogéneos listos para usar. Se encarga de crear y administrar automáticamente el objeto Trace Context entre una pila completa de microservicios implementados en diferentes pilas técnicas.
