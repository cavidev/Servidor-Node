# Servidor-Node
## Guía de ejemplo en la construcción de un servidor en NodeJs.

 **La carpeta Web.Server (servidor) contiene los modulos logicos de controlador, logica y conexión,  cada uno se conecta entre si por medio del export en JavaScript, 
 
 
 Nota: La parte del Frontend no esta implementada aún, si necesita adecuarlo a uno solo cambiar la ruta del /../Web.App donde se encuentre los archivos del nuevo Frondend, en el server.js.. La instacia de Tedious utilizada es la 14 ... una version mas actualizada no soportara la logica del servidor, si quisiera mejorar esa parte seria bueno las recomendaciones.
 
 ```[javascript]
  //Se direccionan las vistas. EL mismos server levanta las vistas, para el caso de AngularJs.
  app.use('/', express.static(__dirname + '/../Web.App'));
  ```
  Dentro de la carpeta Web.Server encontrara los archivos necesarios para montar un servidor en ***NodeJs***, con una ejecución simple del paquete de instalacion (npm install), el package.js contiene las instancias y obtiene los archivos necesario junto con el nucleo de node para ejecutar el servidor y dejarlo correindo en una version de desarrollo, la logica del servidor consiste en:

  **La parte servidor:
  
  Esta contiene los elemento nesesario para configurar el servidor node, los archivos que necesitara y las configuraciones predeterminadas esenciales.
  
   **La parte controlador (Controladores)
   
   Esta sección contendra los controladores a los cuales se les pediran las peticiones, divididas en CRUD hacia la parte de logia.
    ```[javascript]
    exports.peticion = function peticion(request, response) {
        //llamada a uno de las funciones de logica, se puede dividir en funciones CRUD
        logica_NombreModulo_.logicaPeticion(request.body, function(res) {
            response.send(res); //Forma en la que responde el servidor.
        });
    };
    ```
     
   **La parte logica (Lógica)
   
   Esta parte contendra todo lo relacionado con la aritmetica y/o logica del negocio, desde aqui se piden datos a bases de datos, se almacenan, comparar o se revuelven para responderle al cliente.
   
   ```[javascript]
   exports.logicaPeticion = function logicaPeticion(datos, callback) {
          //Funciones de logica, para no sobrecargar al cliente, se ralizan todos los procesos pesados aqui se piden datos desde bases de datos y luego se envian por medio del servidor.
          conexion_NombreModulo_.obtenerDatosDesdeBDs(datos, function(res) {
              var suma = 3 + 4 * 89;
              res.resultado = suma;
              callback(res); //SE DEVUELVE RES
          });
      }
   ```
   
   **La parte conexcion (Conexión)
   
   Dividida en 2 secciones, la primera conecta con las bases de datos prefereridas (archivos de configuracion) y las segundo realiza la conexion desde la logica hacia la base de datos.
   
   Configurar esta parte para la conexión con MongoDB.
   ```[javascript]
   {
       "title": "Archivo configuración de MongoDB",
       "description": "Archivo de configuración con los parámetros necesarios para establecer la conexión a mongodb",
       "params": {
           "host": "",
           "port": ,
           "user": "",
           "password": "",
           "database": ""
       }
   }
    ```
