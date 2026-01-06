# Musicstream 🎵

**Musicstream** es un proyecto de análisis de datos que busca comprobar si lo que pensamos sobre la música realmente coincide con lo que dicen los números. Entre **2010 y 2018**, la industria ha cambiado por completo, y hemos usado las APIs de **Spotify** y **Last.fm** para entender qué ha pasado con cuatro géneros: **Country, Latin, Jazz y Rock**.

### El valor del proyecto
El objetivo general es verificar si nuestra cultura musical y nuestras primeras impresiones encajan con los datos reales de oyentes y popularidad. Queremos descubrir si lo que recordamos es una percepción personal basada en nuestra experiencia o si los datos confirman esas tendencias de manera objetiva.

## 👥 Equipo y Metodología

Para trabajar de manera organizada y eficiente, nos organizamos de la siguient manera:

* **Scrum Master:** Bet Aguiló.
* **Equipo de Desarrollo:**
    * Alba Jalencas.
    * Ana Romero.
    * Fabiana Britez.
    * Patricia Anaya.

## 🛠️ Herramientas utilizadas

Hemos diseñado un sistema para extraer, procesar y almacenar datos con este stack tecnológico:

| Herramienta | Función |
| :--- | :--- |
| **Python** | Lenguaje principal para toda la lógica del proyecto. |
| **Spotipy / Requests** | Conexión con las APIs oficiales de Spotify y Last.fm. |
| **Pandas / NumPy** | Limpieza y tratamiento avanzado de los datos. |
| **MySQL** | Organización y almacenamiento en base de datos. |
| **Matplotlib** | Creación de gráficos y visualización de resultados. |
| **python-dotenv** | Gestión segura de claves y credenciales. |


## 🚀 Estructura del proyecto

El flujo de trabajo se divide en 2 etapas principales:

1.  **Obtención de datos (`CODIGO_FINAL.ipynb`)**
2.  **Análisis (`CONSULTAS_musicstream.ipynb`):** 

## 📊 ¿Dato o Percepción?

Uno de los puntos más interesantes del análisis fue contrastar nuestras expectativas con la realidad de los datos:

> **El hallazgo:** Aunque todas pensábamos que la música **Latina** lideraría el impacto en la era digital, los datos revelaron que el **Rock** mantuvo el liderazgo en términos de oyentes y presencia durante el periodo analizado.

Este resultado demuestra que nuestra percepción cultural no siempre coincide con las métricas globales de las plataformas.

## ⚙️ Configuración

Si quieres replicar el proyecto, solo tienes que crear un archivo llamado `.env` en la raíz con tus credenciales:

```env
# Claves de Last.fm
API_KEY_LASTFM=tu_clave_aqui
SHARED_SECRET_LASTFM=tu_secreto_aqui

# Claves de Spotify
SPOTIFY_CLIENT_ID=tu_id_aqui
SPOTIFY_CLIENT_SECRET=tu_secreto_aqui

# Base de datos
MYSQL_HOST=localhost
MYSQL_USER=root

## 🔹 Actualizaciones del Proyecto – Rama Bet

Una segunda versión del proyecto se encuentra disponible en la rama **Bet**:  
[Bet – Mejoras y Actualizaciones](https://github.com/eaguilothio/da-project-promo-59-modulo-2-team-1/tree/Bet/proyecto_v2_mejoras_y_actualizaciones)

MYSQL_PASSWORD=tu_password
MYSQL_DATABASE=musicstream_db
