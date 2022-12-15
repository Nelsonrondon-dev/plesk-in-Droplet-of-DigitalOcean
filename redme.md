# Inicialización de Plesk en un Droplet de DigitalOcean

Este proyecto describe cómo inicializar Plesk en un Droplet de DigitalOcean.

## Instalación

### Paso 1

Inicia sesión en tu cuenta de DigitalOcean y crea un nuevo Droplet. Puedes elegir la distribución de Linux que prefieras, pero en este ejemplo usaremos Ubuntu.

### Paso 2

Selecciona Marketplace en DigitalOcean y seleccionar "plesk - blog and forum", selecciona el plan, selecciona el Nodo en mi caso San Francisco en el tuyo el que sea más cercano a tu ubicación o la de los usuarios.

### Paso 3

 Crea la clave SSH

### Paso 4 
 
Una vez que se hayan seleccionado todas las opciones, hacer clic en el botón "Create Droplet" para iniciar la creación del drople.

### Paso 5

Una vez que el Droplet se haya creado, conéctate a él mediante SSH. Puedes usar el comando `ssh root@IP_DEL_DROPLET` para conectarte, donde `IP_DEL_DROPLET` es la dirección IP de tu Droplet.

### Paso 6

Una vez conectado, actualiza los paquetes de tu sistema operativo ejecutando el comando `apt-get update`.


### Paso 7 

Agrega un usuario y otorgarle permisos

Para agregar un usuario llamado "dev" y otorgarle permisos, se pueden seguir los siguientes pasos:

1. Acceder al servidor donde se quiere agregar el usuario. Esto se puede hacer mediante una conexión SSH o accediendo directamente al servidor si está disponible.
2. Una vez que se tiene acceso al servidor, utilizar el comando `adduser` para agregar el usuario "dev". Por ejemplo:

`adduser dev`

3. El comando anterior pedirá ingresar una contraseña para el usuario "dev" y algunos datos adicionales. Ingresar la información correspondiente y presionar "Enter" para continuar.
4. Una vez que el usuario "dev" ha sido creado, utilizar el comando `usermod` para agregar el usuario a un grupo con permisos de administrador. Por ejemplo:

`usermod -aG sudo dev`


## Uso


### Paso 1

Una vez que se haya completado la instalación, ejecuta el comando `plesk-login` para inicializar el Plesk.

### Paso 2

Sigue las instrucciones que aparecen en la pantalla para completar la instalación de Plesk. Puedes elegir parámetros de configuración, como el nombre de usuario y contraseña del administrador.


### Paso 3

Una vez que la instalación de Plesk se haya completado, puedes acceder a la interfaz de administración de Plesk usando la dirección IP de tu Droplet y el puerto 8443, por ejemplo: `https://IP_DEL_DROPLET:8443`.

### Paso 4

Agrega un dominio dentro del plesk

 1. Iniciar sesión en el panel administrativo de Plesk.
 2. Hacer clic en el botón "Añadir Dominio".
 3. Introducir el nombre de dominio y seleccionar la opción "Sitio web en blanco" en el menú desplegable.
 4. selecciona las opción Webspace settings
 5. Seleciona un nombre de usuario y contraseña para la conexion FTP
 6. Configurar cualquier otra opción deseada y hacer clic en el botón "Add domain" para agregar el nuevo dominio.

### Paso 5

Activa SSL en el dominio desde el panel de Plesk de Lets Encrypt

1. Inicia sesión en tu cuenta de Plesk.
2. Haz clic en el ícono "Sites" en la barra lateral izquierda.
3. Haz clic en el nombre del sitio web para el cual quieres activar SSL.
4. Haz clic en el botón "Hosting Settings" en la página del sitio web.
5. En la página de "Hosting Settings", busca la sección "Security" y asegúrate de que la opción "Permanent SEO-safe 301 redirect from HTTP to HTTPS" esté habilitada. Esto asegurará que todas las solicitudes a tu sitio web se redirijan automáticamente a la versión segura (HTTPS) del sitio.
6. Haz clic en el botón "Certificates" en la barra lateral izquierda.
7. En la página de "Certificates", haz clic en el botón "Add Certificate".
8. En la página "Add Certificate", selecciona la opción "Let's Encrypt" en el menú desplegable "Certificate provider".
9. En el campo "Hostname", escribe el nombre de dominio para el cual quieres obtener un certificado SSL. Asegúrate de que este nombre sea el mismo que el utilizado para acceder al sitio web
10. Haz clic en el botón "Install".


### Paso 6

Crea una base de datos desde el panel de Plesk

1. Inicia sesión en tu cuenta de Plesk.
2. Haz clic en el ícono "Databases" en la barra lateral izquierda.
3. Haz clic en el botón "Add Database" en la página "Databases".
4. En la página "Add Database", escribe el nombre de la base de datos que quieres crear en el campo "Database name".
5. En el menú desplegable "Database server", selecciona la opción "Local".
6. En el menú desplegable "Database type", selecciona la opción "MariaDB".
7. Haz clic en el botón "OK" para crear la base de datos.


