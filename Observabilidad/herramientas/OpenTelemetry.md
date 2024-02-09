# OpenTelemetry

OpenTelemetry es un proyecto que surgió de la fusión de OpenCensus y OpenTracing en 2019. Algunas funciones de OpenTelemetry aún están en versión beta.
OpenTelemetry es un estándar de observabilidad de código abierto que define cómo generar, recopilar y describir telemetría en sistemas distribuidos.

- Proporciona un conjunto de API, SDK y bibliotecas de instrumentación que implementan el estándar, que puede recopilar, procesar y orquestar datos de telemetría como trazas, métricas y logs.
- Admite múltiples lenguajes populares (Java, .NET, Python, JavaScript, Golang, Erlang, etc.).
- La telemetría abierta sigue un enfoque independiente del proveedor y basado en estándares para recopilar y gestionar datos de telemetría.
- OpenTelemetry no tiene su propio backend; toda la telemetría recopilada debe enviarse a un backend como Prometheus, Jaeger, Zipkin, Azure Monitor, etc.

## ¿Por qué utilizar OpenTelemetry?

- Ofrece un estándar de código abierto para implementar telemetría distribuida (propagación de contexto) en sistemas heterogéneos.

  ![Automatic and Manual Telemetry](../images/contextpropagation.png)

- Permite tracing, métricas y logs a través de un conjunto de bibliotecas y herramientas multilingües que permiten una arquitectura de telemetría plug-and-play que incluye el concepto de agentes y recopiladores.

  ![Collectors option](../images/newarchitecture.png)

- Evita cualquier bloqueo de propiedad y lograr una neutralidad independiente del proveedor.
- Además de agregar atributos personalizados, muestreo, recopilación de datos para métricas y trazas, OpenTelemetry se rige por especificaciones y está respaldado por grandes actores como Microsoft, Splunk, AppDynamics, etc.
- OpenTelemetry se está convirtiendo en un estándar de-facto.
