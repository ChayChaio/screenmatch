# ScreenMatch - Proyecto de Base de Datos y App Web

Este proyecto permite cargar y gestionar una base de datos de **series** utilizando la API de OMDB, con traducción automática de sinopsis mediante la API de OpenAI. La aplicación incluye un **frontend** que depende de los datos previamente cargados para funcionar correctamente.
Al acceder desde el frontend el usuario puede visibilizar los posters de las series de la base de datos separadas en 3 categorías.
   1. Lanzamientos en Screenmatch: muestra las últimas 5 series en lanzar nuevos episodios.
   2. Títulos populares en Screenmatch: muestra las 5 series mejor puntuadas.
   3. Títulos en Screenmatch: muestra todas las series cargadas.

También el usuario tiene la opción de filtrar series según su género mediante un menú desplegable al inicio de la página.

Además de esto, al seleccionar el usuario una serie clickeando en su poster puede acceder a la información de dicha serie:
   - Poster
   - Título
   - Promedio de evaluaciones
   - Sinópsis
   - Actores
   - Temporadas

Al clickear en el dropbox de temporadas uno puede elegir ver el detalle de todas, o de alguna en particular.
Al seleccionar alguna opción aparecen los capítulos por temporadas con sus respectivos nombres.

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
**Base de datos**

La conexión con la base de datos está configurada con variables de entorno que dirigen a una base de datos local. Esto se puede modificar a gusto del usuario dentro del archivo `application.properties`.

**Uso con el Frontend**
- Archivo principal: `ScreenmatchApplication.java`
- Este archivo gestiona la conexión entre el backend y el frontend.

Nota:
Si la base de datos no se ha llenado correctamente con `ScreenmatchApplicationConsola.java`, la aplicación web no podrá acceder a los datos necesarios para funcionar.

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

**Instrucciones de Uso**
1. Configuración de las API Keys
   - En `Principal.java`, ingresa tu API key de OMDB.
   - En `ConsultaChatGPT.java`, ingresa tu API key de OpenAI.

2. Ejecución desde la Consola
   - Compila `ScreenmatchApplicationConsola.java`:
```bash
javac ScreenmatchApplicationConsola.java
```

- Ejecuta:
```bash
java ScreenmatchApplicationConsola
```

3. Verificación de los Datos Cargados
- Asegúrate de que la base de datos tiene las series cargadas antes de proceder al frontend.

4. Deploy del Frontend
- Compila y ejecuta `ScreenmatchApplication.java`:
```bash
javac ScreenmatchApplication.java
java ScreenmatchApplication
```
- El frontend ya podrá acceder a la información en la base de datos.

**Solución de Problemas**
- No Funciona la Traducción:
   - Verifica que la API key de OpenAI se ingresó correctamente en ConsultaChatGPT.java.

- Error al Consumir la API de OMDB:
   - Asegúrate de que la API key en Principal.java es válida y tienes conexión a Internet.

**Contribuciones**
¡Las contribuciones son bienvenidas! Si encuentras un error o quieres mejorar algo, no dudes en abrir un pull request.

**Licencia**
Este proyecto está distribuido bajo la licencia MIT.
