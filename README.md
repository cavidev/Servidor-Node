# Servidor-Node
Guía de ejemplo en la construcción de un servidor en NodeJs.

** La carpeta Web.Server (servidor) contiene los archivos necesarios para montar un servidor en NodeJs, con una ejecion simpre del paquete de instalacion (npm install) packaje se obtiene los archivos necesario junto con el nucleo de node para ejecutar el servidor y dejarlo correindo en una version de desarrollo, la logica del servidor consiste en:

  **La parte servidor:
  
  Esta contiene los elemento nesesario para configurar el servidor node, los archivos que necesitara y las configuraciones predeterminadas esenciales.
  
   **La parte controlador
   
   Esta seccion contendra los controladores a los cuales se les pediran las peticiones, divididas en CRUD hacia la parte de logia.
   
   **La parte logica
   
   Esta parte contendra todo lo relacionado con la aritmetica y/o logica del negocio, desde aqui se piden datos a bases de datos, se almacenan, comparar o se revuelven para responderle al cliente.
   
   **La parte conexcion
   
   Dividida en 2 secciones, la primera conecta con las bases de datos prefereridas (archivos de configuracion) y las segundo realiza la conexion desde la logica hacia la base de datos.
