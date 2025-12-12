
# 📘 Carga de Librerías y Preparación del Entorno

Este documento explica las librerías utilizadas en el proyecto y su propósito, diferenciando entre las que vienen incluidas con Python y las que requieren instalación adicional.

---

### 🔹 Librerías de la Biblioteca Estándar de Python

Estas librerías vienen instaladas por defecto con Python.
No requieren `pip install` y permiten resolver tareas comunes sin dependencias externas.

---

### **`import os`**

`os` significa **“operating system”**. Sirve para interactuar con el sistema operativo:

* Crear, leer o eliminar carpetas y archivos
* Construir rutas de forma segura
* Acceder a **variables de entorno** (ideal para claves privadas como API Keys)

Se usa típicamente junto con `.env` para proteger credenciales sensibles.

---

### **`import time`**

Permite manejar el tiempo en el programa.

* `time.sleep(segundos)` crea pausas controladas
* Muy útil para evitar errores de **rate limit** (como 429) en APIs que restringen el número de peticiones
* Ayuda a que tus scripts sean más respetuosos con los servicios externos

---

## 🔹 Librerías Externas

Estas NO vienen instaladas con Python.
Debes instalarlas con:

```bash
pip install nombre_paquete
```

> Se recomienda registrarlas en un archivo `requirements.txt` para mantener el proyecto ordenado.

---

### **`import pandas as pd`**

`pandas` es la librería más usada para análisis y manipulación de datos.

* Trabaja con datos tabulares (similar a Excel pero en código)
* El alias `pd` es una convención universal
* Ideal para analizar, limpiar o transformar grandes volúmenes de datos

---

### **`import spotipy`**

Cliente oficial de Python para interactuar con la **API de Spotify**.

* Permite obtener metadatos de canciones, artistas, playlists, etc.
* Facilita autenticación y consultas sin manejar las peticiones HTTP directamente

---

### **`from spotipy.oauth2 import SpotifyClientCredentials`**

Maneja la autenticación con Spotify mediante **Client Credentials** (OAuth 2.0).

* Requiere `Client ID` y `Client Secret`
* **No los escribas nunca directamente en el código**
* Lo seguro es cargarlos desde variables de entorno (`dotenv`)
* Ideal para proyectos donde necesitas acceder a datos públicos de Spotify.

---

## ✅ Resumen

Esta configuración te permite:

* Acceder de forma segura a la API de Spotify
* Manipular datos de forma profesional con pandas
* Evitar problemas con límites de uso mediante pausas controladas
* Mantener limpio y seguro tu entorno de trabajo


