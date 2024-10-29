# ScreenMatch - Proyecto de Base de Datos y App Web

Este proyecto permite cargar y gestionar una base de datos de **series** utilizando la API de OMDB, con traducción automática de sinopsis mediante la API de OpenAI. La aplicación incluye un **frontend** que depende de los datos previamente cargados para funcionar correctamente.

---

## Estructura del Proyecto

### Uso desde la Consola
- **Archivo principal:** `ScreenmatchApplicationConsola.java`  
- Este archivo consume la API de OMDB para obtener información de series y la carga en la base de datos.  
- **Traducción de sinopsis:** Integrada mediante la API de OpenAI.  

**API Keys requeridas:**
1. **OMDB:**  
   Debes ingresarla en el archivo `Principal.java`:
   ```java
   private static final String API_KEY_OMDB = "TU-API-KEY";
2. **OpenAI:**  
   Debes ingresarla en el archivo `ConsultaChatGPT.java`:
   ```java
   private static final String API_KEY = "TU-API-KEY";
   ```

**Uso con el Frontend**
- Archivo principal: `ScreenmatchApplication.java`
- Este archivo gestiona la conexión entre el backend y el frontend.

Nota:
Si la base de datos no se ha llenado correctamente con ScreenmatchApplicationConsola.java, la aplicación web no podrá acceder a los datos necesarios para funcionar.

**Estructura del Frontend**
- El frontend se encuentra en la carpeta screenmatch-frontend e incluye los siguientes archivos:
   - HTML:
      - `index.html`: Página de inicio.
      - `detalles.html`: Página de detalles de una serie.
   - CSS:
      - `styles.css`: Estilos generales.
      - `css/home.css`: Estilos específicos para la página principal.
      - `css/detalhes.css`: Estilos para los detalles de las series.
   - JavaScript:
      - `scripts/index.js`: Lógica de la página principal.
      - `scripts/series.js`: Gestión de datos de las series.
      - `scripts/getDatos.js`: Consulta de datos desde la API.

**Requisitos Previos**
- Java 8 o superior instalado.
- Acceso a Internet para consumir las APIs de OMDB y OpenAI.
- API Keys:
      - OMDB
      - OpenAI
Instrucciones de Uso
1. Configuración de las API Keys
En Principal.java, ingresa tu API key de OMDB.
En ConsultaChatGPT.java, ingresa tu API key de OpenAI.
2. Ejecución desde la Consola
Compila ScreenmatchApplicationConsola.java:
bash
Copiar código
javac ScreenmatchApplicationConsola.java
Ejecuta:
bash
Copiar código
java ScreenmatchApplicationConsola
3. Verificación de los Datos Cargados
Asegúrate de que la base de datos tiene las series cargadas antes de proceder al frontend.

4. Deploy del Frontend
Compila y ejecuta ScreenmatchApplication.java:
bash
Copiar código
javac ScreenmatchApplication.java
java ScreenmatchApplication
El frontend ya podrá acceder a la información en la base de datos.
Solución de Problemas
No Funciona la Traducción:

Verifica que la API key de OpenAI se ingresó correctamente en ConsultaChatGPT.java.
Error al Consumir la API de OMDB:

Asegúrate de que la API key en Principal.java es válida y tienes conexión a Internet.
Contribuciones
¡Las contribuciones son bienvenidas! Si encuentras un error o quieres mejorar algo, no dudes en abrir un pull request.

Licencia
Este proyecto está distribuido bajo la licencia MIT.
