# Databricks Vector Search

A diferencia de otras bases de datos, Databricks Vector Search admite la sincronización automática de datos desde el origen hasta el índice, lo que elimina el mantenimiento complejo y costoso de pipelines. Aprovecha las mismas herramientas de seguridad y gobierno de datos que las organizaciones ya han creado para su tranquilidad. Con su diseño serverless, Databricks Vector Search se escala fácilmente para admitir miles de millones de embeddings y miles de consultas en tiempo real por segundo.

- Construido para retrieval augmented generation (RAG)

  Databricks Vector Search está diseñado específicamente para que los clientes aumenten sus modelos LLM con datos empresariales. Diseñado específicamente para aplicaciones RAG, Databricks Vector Search ofrece resultados de búsqueda similares, enriqueciendo las consultas LLM con contexto y conocimiento del dominio, y mejorando la precisión y la calidad de los resultados.

- Pipelines automatizadas en tiempo real

  Sincronización en tiempo real de los datos de origen actualizando automáticamente el índice vectorial correspondiente a medida que se agregan, modifican o eliminan nuevos datos. Internamente, Databricks realiza la generación y administración de vectores embedding, y administra automáticamente las fallas, maneja los reintentos, optimiza el rendimiento y realiza ajustes de escala automáticos sin necesidad de ninguna intervención.

- Gobernanza incorporada

  La interfaz unificada define políticas sobre datos. Con integración incorporada con Unity Catalog, Vector Search muestra el linaje y el seguimiento de datos automáticamente sin necesidad de herramientas o políticas de seguridad adicionales. Esto garantiza que los modelos LLM no expongan datos confidenciales a usuarios que no deberían tener acceso.

- Rendimiento rápido de consultas

  Se escala automáticamente para manejar miles de millones de embeddings en un índice y miles de consultas por segundo. Muestra un rendimiento hasta 5 veces más rápido que otras bases de datos vectoriales líderes en datasets de hasta 1 millón de embedding  de OpenAI.
