# grupo_1_proyecto_2_music_stream

# 🎶 MusicStream
*Análisis musical con datos reales de Spotify y Last.fm*

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

## Procesamiento
- Se genera un archivo **CSV por año**, integrando los datos de Spotify y Last.fm  
- La información se organiza de manera **coherente y consistente**, facilitando su análisis y posterior carga en la base de datos

---

### 2. Almacenamiento de la información
## Base de datos
- Se utiliza una **base de datos relacional (SQL)** para un manejo estructurado y eficiente de la información.
## Tablas
- **Tablas principales e intermedias:** los datos se organizan en tablas base y tablas de relación, facilitando consultas, análisis y mantenimiento.
## Inserción de datos
- Los datos recolectados se insertan de manera **ordenada y coherente**, asegurando la **integridad y consistencia** de la información.

---

### 3. Análisis y conclusiones
- Consultas SQL: análisis de los datos para extraer conclusiones sobre tendencias musicales, popularidad de artistas, patrones de consumo y relaciones entre producción y recepción.

---

## 🧠 Metodología
Trabajamos con **Agile + Scrum**, con roles:  
- **Scrum Master:** facilita el flujo  
- **Equipo de desarrollo:** construye y valida el análisis  