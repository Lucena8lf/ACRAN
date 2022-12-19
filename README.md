# FRONTEND

### Introducción

Para el frontend se ha utilizado Android Studio, haciendo uso del lenguaje Java.

### Importar el proyecto en Android Studio

Para importar el proyecto siga los siguientes pasos:

1. Descomprimir el archivo .zip
2. Abrir Android Studio
3. Ir a File > Open
4. Seleccionar la carpeta que resulta de la descompresión del .zip

### Configuración

Como la aplicación funciona con un servidor remoto ésta requiere de almacenar la IP del servidor con el que se comunica.

Para establecer la IP del server modifique el string "IP_server" del archivo res/values/strings.xml. Por defecto viene con la IP del server que se ha utilizado para poner el backend en producción.

### Crear APK

Para crear la APK, haga click en Build > Build Bundle(s) / APK(s) > Build APK(s)

# BACKEND

### Introducción

Para el backend se ha utilizado el framework NodeJS, el cual utiliza el lenguaje JavaScript. Por lo tanto, es necesario que se tenga instalado el cual se puede descargar de forma gratuita desde su página oficial.

### Dependencias

Las dependencias o módulos de producción con los que cuenta el proyecto son:

- express
- mysql2
- morgan
- cors
- swagger-jsdoc
- swagger-ui-express
- dotenv
- moment

Para instalarlas, ejecutar en la terminal:

	npm i express mysql2 morgan cors swagger-jsdoc swagger-ui-express dotenv moment

Por otro lado, las dependencia de desarrollo son las siguientes:

- nodemon
- @babel/core
- @babel/cli
- @babel/preset-env
- @babel/node

Para instalarlas, ejecutar en la terminal:

	npm i nodemon @babel/core @babel/cli @babel/preset-env @babel/node -D

### Scripts del proyecto

El proyecto cuenta con los siguientes scripts a la hora de trabajar:

- build (npm run build): es el primer script que hay que ejecutar al bajar por primera vez el proyecto o al tener una versión nueva del mismo. Este script se encarga de transpilar todo el código a babel.
- dev (npm run dev): es un script para desarrollo. Este ejecutará el proyecto con nodemon en vez de con node, el cual irá reiniciando el servidor cada vez que detecte nuevos cambios.
- start (npm start): script que arranca el servidor ejecutándolo con node .

### Documentación

Este proyecto cuenta con documentación de todas las rutas existentes. Esta documentación ha sido realizada con Swagger y se puede acceder en la ruta "/docs".

### Variables de entorno

Las variables de entorno son variables externas a la aplicación que residen en el sistema operativo o en el contenedor de la aplicación que se está ejecutando. Este proyecto trabaja con ellas y deben estar en el archivo ".env", por lo que se deberá crear un archivo con esa extensión y asignar todas las variables necesarias para el proyecto de acuerdo a la persona que esté utilizando el código.

Para facilitarlo el proyecto cuenta con un archivo ".env.example" el cual contiene todas las variables de entorno necesarias y la sintaxis para asignar cada valor a las mismas.

# Base de datos

### Información

El script para la creación de la base de datos se adjunta en el fichero bd.sql.

Para evitar problemas con los triggers, se recomienda usar sudo para crear la base de datos:

	sudo mysql <database> < bd.sql