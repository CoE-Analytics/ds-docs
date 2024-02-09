# Logging

## Mejores prácticas

- Preste atención a los niveles de log. Registrar demasiado aumentará los costos y disminuirá el rendimiento de la aplicación.
- Asegúrese de que la configuración de log se pueda modificar sin cambios de código.
- Si está disponible, aproveche los niveles de log por categoría, lo que permite una configuración de log granular.
- Logee una excepción generada solo una vez. En sus controladores, solo capture las excepciones esperadas que pueda manejar correctamente. No registre una advertencia ni un seguimiento de la pila para las excepciones esperadas.
- Ajuste los niveles de log en producción. Durante una nueva versión, se puede aumentar la detalle para facilitar la identificación de errores.
- Si utiliza muestreo, impleméntelo en el nivel de servicio en lugar de definirlo en el sistema de log. De esta manera tenemos control sobre lo que se registra. Un beneficio adicional es la reducción del número de viajes de ida y vuelta.
- Incluya únicamente errores de comprobaciones de estado y solicitudes no impulsadas por el negocio.
- Asegúrese de que un mal funcionamiento del sistema posterior no provoque el almacenamiento de logs repetitivos.
- No reinvente la rueda, utilice las herramientas existentes para recopilar y analizar los datos.
- Asegúrese de que se sigan las políticas y restricciones de información de identificación personal.
- Asegúrese de que los errores y excepciones en los servicios dependientes se capturen y registren.

## Que se debe logear?

**Al iniciar la aplicación:**

- Errores irrecuperables desde el inicio.
- Advertencias si la aplicación aún se puede ejecutar, pero no como se esperaba.
- Información sobre el estado del servicio al inicio.

**Por request entrante:**

- Información básica para cada request entrante: URL, cualquier dimensión de usuario/inquilino/request, código de respuesta devuelto, latencia, tamaño, recuentos de registros, etc.
- Advertencia sobre excepciones inesperadas, detectadas solo en el controlador/interceptor superior y registradas con o junto con la información de request, con seguimiento de pila. Devuelve un 500. Este código no sabe lo que pasó.

**Por request saliente:**

- Información básica para cada request saliente: URL, cualquier dimensión de usuario/inquilino/request, código de respuesta devuelto, latencia, tamaño, recuentos de registros, etc. Informe la disponibilidad percibida y la latencia de las dependencias e incluya datos de división/agrupación que podrían ayudar con el análisis posterior.

## Herramientas recomendadas

- **Azure Monitor**: conjunto de servicios que incluyen métricas del sistema, log analytics y más.
- **Grafana Loki**: una plataforma de agregación de registros de código abierto, basada en los aprendizajes de la comunidad Prometheus para una recopilación y almacenamiento altamente eficiente de datos de registros a escala.
- **The Elastic Stack**: una pila de tecnología de análisis de registros de código abierto que utiliza Logstash, Beats, Elastic search y Kibana.
- **Grafana**: dashboard y herramienta de visualización de código abierto. Admite fuentes de datos de logs, métricas y trazas distribuidas.
