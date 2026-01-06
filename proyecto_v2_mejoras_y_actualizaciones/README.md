# MusicStream – README Version 2

La versión 1 corresponde al trabajo grupal, mientras que la versión 2 refleja las **mejoras individuales desarrolladas por Bet**, orientadas a mejorar la claridad, reforzar la seguridad y aplicar buenas prácticas.
 
El proyecto analiza la música entre **2010 y 2020** (ampliando el periodo original de 2010 a 2018), considerando los años **2010, 2012, 2014, 2016, 2018 y 2020**, y los géneros **Country, Latin, Jazz y Rock**, utilizando datos de **Spotify** y **Last.fm**.

## Principales mejoras 

- **Funciones seguras:** `spotify_search_seguro` y `spotify_album_tracks_seguro` con manejo de errores y reintentos automáticos.
- **Integración de datos:** los datos se organizan en **dos tablas** (`canciones` y `datos_lastfm`) dentro de MySQL, asegurando información consistente y completa.
- **Consultas y gráficos optimizados:** visualizaciones más claras y consultas eficientes, facilitando la interpretación de tendencias y comparaciones.
- **Código limpio y mantenible:** reorganización de notebooks en fases (1, 2, 3), con funciones estructuradas y procesos documentados para facilitar su comprensión y mantenimiento.

## Pendiente
- Integrar los CSV correspondientes a **2018 y 2020** y finalizar el análisis de todos los años.


