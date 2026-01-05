# MusicStream – README de Mejora Individual Postevaluación

Esta versión refleja **mejoras individuales posteriores a la evaluación**, centradas en claridad, seguridad y buenas prácticas. El proyecto analiza la música entre **2010 y 2020** (ampliando el periodo original hasta 2018), enfocándose en los géneros **Country, Latin, Jazz y Rock**, usando datos de **Spotify** y **Last.fm**.

## Principales mejoras individuales

- **Funciones seguras:** `spotify_search_seguro` y `spotify_album_tracks_seguro` con manejo de errores y reintentos automáticos.
- **Integración de datos:** los datos se organizan en **dos tablas** (`canciones` y `datos_lastfm`) dentro de MySQL, asegurando información consistente y completa.
- **Consultas y gráficos optimizados:** visualizaciones más claras y consultas eficientes, facilitando la interpretación de tendencias y comparaciones.
- **Código limpio y mantenible:** reorganización de notebooks en fases (1, 2, 3), con funciones bien estructuradas, nombres claros y procesos documentados, asegurando que el código sea fácil de entender, reutilizar y mantener.

- **Pendiente:** integrar los CSV de 2018 y 2020 para completar la fase de postevaluación.

