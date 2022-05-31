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
Esto ocurre de forma automática al ejecutar la API, nos arroja un "OK" una vez lograda la conexión.

* Creación de usuario
Colocamos el request en ```POST``` y la dirección ```localhost:3000/crearUsuario```. En el body del request, en formato JSON, ponemos los parametros de:
```
"nombreDeUsuario": "ingrese nombre",
"clave": "ingrese clave",
"idEvento": "ingrese idEvento"
```
Esto nos devolverá un "OK" si la creación de usuario fue exitosa. En caso contrario, nos devolverá un "NOK"

* Autenticación de usuario
Colocamos el request en ```GET``` y la dirección ```localhost:3000/autenticar/:nombreDeUsuario/:clave/:idEvento```, donde ":nombreDeUsuario" será reemplazado por el usuario que será autenticado, ":clave" igualmente será reemplazada por la clave del usuario a autenticar, y ocurre lo mismo con ":idEvento".
Esto nos devolverá la id del usuario que ha sido autenticado. En caso contrario, se devolverá un "NOK".

* Borrar todos los usuarios
Colocamos el request en ```GET``` y la dirección ```localhost:3000/borrarUsuarios```, esto borrará todos los usuarios en la base de datos. Para la comprobación de esto, se devuelve la colección de usuarios antes de ser borrada y después del borrado por medio de la consola.

* Cargar usuarios por medio de archivo CSV
{Colocamos el request en ```POST``` y la dirección ```localhost:3000/cargarCsv```. Adicionalmente, en el request cargamos el archivo CSV que se quiere mandar.
```
nombreDeUsuario,clave,idEvento
```
Ese debe ser el formato del CSV que se envie.
Cuando mandemos el request, se crearan los usuarios correspondientes al archivo y por cada usuario que se cree se devolverá un "OK"}
