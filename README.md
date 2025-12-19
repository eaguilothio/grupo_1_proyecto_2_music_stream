# grupo_1_proyecto_2_music_stream

# 🎶 MusicStream
*Análisis musical de 2010 a 2018 con datos reales de Spotify y Last.fm*

> Proyecto del Módulo 2 realizado por **5 mujeres apasionadas por la música y los datos**.  
> Objetivo: hacer un **análisis de datos** de cómo evolucionaron géneros, artistas y canciones entre 2010 y 2018.

---

## 🎯 Objetivo
Analizar la **evolución de la música** entre 2010 y 2018 a partir de datos de **Spotify** y **Last.fm**, centrándonos en **"country","latin","jazz","rock"**.  

Buscamos mostrar de manera clara cómo evolucionaron los géneros, cuáles artistas se mantuvieron activos a lo largo de los años y qué canciones o álbumes alcanzaron mayor popularidad.

---

## 🛠️ Cómo lo hicimos

### 1. Extracción de datos 

## Datos obtenidos
- **Rango temporal:** 2010–2018 (cada 2 años: 2010, 2012, 2014, 2016, 2018)  
- **Géneros musicales:** country, latin, jazz, rock  

## Plataformas y campos
- **Spotify API:** artista, género, tipo (canción o álbum), nombre, año, cantidad de canciones  
- **Last.fm API:** biografía, número de oyentes (*listeners*), reproducciones (*playcount*), artistas similares  


---

### 2. Almacenamiento de la información

- **Base de datos**: se utiliza para almacenar y gestionar la información de forma estructurada y eficiente.
- **Tabla base**: todos los datos se concentran en una sola tabla, evitando la complejidad de relaciones y tablas intermedias.
- **Carga de datos**: se genera un archivo CSV consolidado con la información de todos los años, integrando datos de Spotify y Last.fm, que luego se utiliza para la inserción en la base de datos.

---

### 3. Análisis y conclusiones
- **Consultas analíticas**: se exploran los datos para identificar tendencias musicales, evaluar la popularidad de artistas y detectar patrones de consumo, a partir de preguntas de interés analítico.

---

## 🧠 Metodología
Trabajamos con **Agile + Scrum**, con roles:  
- **Scrum Master:** facilita el flujo  
- **Equipo de desarrollo:** construye y valida el análisis  


---
---
---
---
---
---


# Musicstream 🎵

**Musicstream** es un proyecto de análisis de datos enfocado en la **evolución de la música entre 2010 y 2018**. Utilizando datos extraídos de las APIs de **Spotify** y **Last.fm**, el equipo se ha centrado en analizar cuatro géneros clave: **Country, Latin, Jazz y Rock**.

El objetivo principal es visualizar cómo han evolucionado estos géneros, identificar a los artistas más constantes a lo largo del tiempo y determinar qué lanzamientos alcanzaron mayor impacto en términos de popularidad y oyentes.

---

## 👥 Equipo y Metodología

Este proyecto se ha desarrollado bajo la **Metodología Scrum**, asegurando una entrega iterativa y una comunicación fluida. Para garantizar la integridad del código y facilitar el trabajo colaborativo, hemos implementado un **flujo de trabajo basado en ramas (Git Flow)**, permitiendo que cada funcionalidad o corrección se desarrollara de forma aislada antes de integrarse en la rama principal.

* **Scrum Master:** Bet Aguiló.
* **Equipo de Desarrollo:**
    * Alba Jalencas.
    * Ana Romero.
    * Fabiana Britez.
    * Patricia Anaya.

---

## 🛠️ Tecnologías Utilizadas

Para el desarrollo del sistema ETL y el análisis posterior, se han empleado las siguientes herramientas:

* **Control de Versiones:** **GitHub** (Gestión de repositorio y flujo de trabajo por ramas).
* **Lenguaje:** Python 3.x.
* **Librerías principales:**
    * `Pandas` y `NumPy`: Para la manipulación y limpieza de datos.
    * `Spotipy`: Cliente de Python para la API de Spotify.
    * `Requests`: Para realizar peticiones HTTP a la API de Last.fm.
    * `MySQL Connector`: Para la gestión e inserción de datos en la base de datos relacional.
    * `Matplotlib`: Para la generación de visualizaciones de los insights.
    * `python-dotenv`: Para la gestión segura de credenciales mediante variables de entorno.

---

## 🚀 Estructura del Proyecto

El flujo de trabajo se divide en los siguientes componentes principales:

1.  **Extracción e Inserción (`CODIGO_FINAL.ipynb`):**
    * Conexión con las APIs de Spotify y Last.fm.
    * Proceso de limpieza de datos (manejo de nulos con `numpy.nan` y `None`).
    * Carga masiva de datos en una base de datos MySQL denominada `musicstream_db`.

2.  **Análisis y Consultas (`CONSULTAS_musicstream.ipynb`):**
    * Ejecución de consultas SQL directamente desde Python.
    * Generación de métricas clave sobre popularidad y producción musical.

3.  **Datos:**
    * `TABLA_FINAL.csv`: Dataset consolidado con información de canciones, artistas, álbumes, géneros, años de lanzamiento y número de oyentes.

---

## 📊 Insights Clave

A través del análisis realizado, el proyecto responde a preguntas estratégicas como:
* **Artistas Top:** Identificación de los 10 artistas más populares (ej. Radiohead, Nirvana, Red Hot Chili Peppers).
* **Tendencias:** Géneros que predominaron en lanzamientos durante el periodo analizado.
* **Producción:** Identificación de los picos y valles en la producción musical por año.

---

## ⚙️ Configuración

Para replicar este proyecto, asegúrate de configurar tu archivo `.env` basándote en el archivo de ejemplo proporcionado:

```env
# --- CREDENCIALES API LAST.FM ---
# Consíguelas en: https://www.last.fm/api/account/create
API_KEY_LASTFM=tu_api_key_aqui
SHARED_SECRET_LASTFM=tu_shared_secret_aqui

# --- CREDENCIALES API SPOTIFY ---
# Consíguelas en: https://developer.spotify.com/dashboard
SPOTIFY_CLIENT_ID=tu_client_id_aqui
SPOTIFY_CLIENT_SECRET=tu_client_secret_aqui

# --- CONFIGURACIÓN BASE DE DATOS MYSQL ---
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=tu_contraseña_aqui
MYSQL_DATABASE=musicstream_db