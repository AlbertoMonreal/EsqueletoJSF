## Instrucciones para compilar y ejecutar la imagen Docker.

1. **Pre-requisitos**:
    - Asegúrate de tener los archivos `ROOT.war` y `Dockerfile`.
    - El archivo `.war` se crea recompilando la aplicación una vez ejecutado el siguiente comando Maven:
     `mvn clean package`
    - Este comando reconstruye la carpeta `target` y crea una nueva versión del archivo `ROOT.war`.
	- El `Dockerfile` está configurado para crear una imagen Docker que incluye el archivo `ROOT.war` en un servidor Tomcat, mapeando el puerto 8080 y eliminando las aplicaciones predeterminadas de Tomcat que están en la carpeta "webapps".
	El archivo ROOT.war se coloca en la raíz del servidor gracias a su propio nombre. Esto hace que Tomcat lo reconozca como la aplicación principal y la sirva desde la ruta raíz (http://localhost:8080).
	Puedes guardar el `Dockerfile` dentro de la raíz del proyecto si te es más cómodo.

2. **Construye la imagen Docker**:
	- Abre una terminal en la carpeta donde están los archivos y ejecuta el siguiente comando:
     `docker build -t esqueletotomcat .`
	- El nombre de la imagen(esqueletotomcat) puede ser cualquiera, solo cámbialo.
	
3. **Ejecuta el contenedor Docker**:
   - Para ejecutar el contenedor, usa el comando:
     `docker run -p 8080:8080 esqueletotomcat`
   - Esto mapea el puerto 8080 del contenedor al puerto 8080 local.

4. **Accede a la aplicación**:
   - Abre tu navegador y visita `http://localhost:8080` para ver la aplicación en ejecución dentro del contenedor Docker.
