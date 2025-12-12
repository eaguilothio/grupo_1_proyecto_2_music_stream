# 🔑 Obtener tu **Client ID** y **Client Secret** de Spotify

Sigue estos pasos para crear una aplicación en el **Spotify Developer Dashboard** y obtener las credenciales necesarias para usar la Web API.

---

## 🚀 1. Acceder al panel de desarrolladores

1. Entra en el **Spotify Developer Dashboard**:  
   https://developer.spotify.com/dashboard  
2. Inicia sesión con tu cuenta de Spotify.

---

## 🆕 2. Crear una nueva aplicación

1. Haz clic en **"Create an App"**.  
2. Completa el formulario con los datos básicos de tu proyecto:
   - **App name**: `Mi proyecto MusicStream`
   - **App description**: `Proyecto educativo para extraer y analizar datos de artistas en géneros como flamenco, reguetón, jazz y rock`
3. Marca la opción: **"I only use the Web API"**  
4. Haz clic en **"Create"**

---

## 🔐 3. Obtener credenciales de la aplicación

Una vez creada la app:

- Copia el **Client ID**
- Haz clic en **"SHOW CLIENT SECRET"** para copiar tu **Client Secret**

> ⚠️ **Importante:** No compartas estas credenciales ni las subas a repositorios públicos.

---

## 🔁 4. Configurar Redirect URI

En la sección **"Redirect URIs"**, añade exactamente esta URL: http://127.0.0.1:8888/callback

Spotify mismo la muestra en su documentación oficial como la dirección de ejemplo que debes usar por defecto cuando trabajas desde tu ordenador ( seccion: Authorization Code Flow).


