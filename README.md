# Docker Web API
## Lenguaje y Base de datos
* Javascript con nodeJS
* MongoDB
## Instalación y ejecución
```
docker-compose build
```
```
docker-compose up
```
Con esto construimos e iniciamos la aplicación.
## Funcionalidades
Nos dirijimos a insomnia REST para probar la aplicación.
* Conexión con la base de datos
Esto ocurre de forma automatica al ejecutar la API, nos arroja un "OK" una vez lograda la conexión.
* Creación de usuario
Colocamos el request en POST y la dirección localhost:3000/crearUsuario. En el body del request, en formato JSON, ponemos los parametros de:
```
"nombreDeUsuario": "ingrese nombre",
"clave": "ingrese clave",
"idEvento": "ingrese idEvento"
```
Esto nos devolverá un "OK" si la creación de usuario fue exitosa. En caso contrario, nos devolverá un "NOK"
* Autenticación de usuario
Colocamos el request en GET y la dirección ```localhost:3000/autenticar/:nombreDeUsuario/:clave/:idEvento```, donde ":nombreDeUsuario" será reemplazado por el usuario que será autenticado, ":clave" igualmente será reemplazada por la clave del usuario a autenticar, y ocurre lo mismo con ":idEvento".
