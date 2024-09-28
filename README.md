# osTicketAPIUsuarios
Implementacion de un API para la creacion de usuarios para Osticket sin la necesidad de la confirmacion por correo por parte del usuario
# Pre-Requisitos
Antes de comenzar, asegúrate de cumplir con los siguientes requisitos:

Servidor Web: Debes tener un servidor web que soporte PHP y MySQL. Se recomienda usar Apache o Nginx.
PHP: Asegúrate de tener PHP instalado. La versión recomendada es PHP 7.2 o superior. Puedes verificar tu versión de PHP ejecutando el siguiente comando:
Extensiones de PHP: Las siguientes extensiones de PHP son necesarias:
mysqli
curl
mbstring
xml
json
Base de Datos MySQL: Necesitarás tener una instancia de MySQL configurada. Puedes usar MySQL o MariaDB. Asegúrate de crear una base de datos para osTicket.
osTicket: Descarga la última versión de osTicket desde el sitio oficial. Descomprime los archivos y colócalos en tu servidor web.
Configuración del entorno: Asegúrate de configurar el archivo de configuración de osTicket (config.php) con los datos correctos de la base de datos.
Acceso a la Red: Verifica que tu servidor tenga acceso a Internet, ya que podría necesitar descargar dependencias o comunicarse con otros servicios.
Siguiendo estos pasos, deberías estar listo para comenzar con la implementación de la API de osTicket.

Puedes instalar osticket desde el siguiente [Link](https://osticket.com/download/).

Recomendable seguir la documentacion por parte de Osticket para la correcta configuracion e instalacion [Documentacion](https://docs.osticket.com/en/latest/Getting%20Started/Installation.html).
# Instalacion
El repositorio puede ser clonado en tu entorno de desarrollo, descargado o simplemente puedes modificar el archivo upload\api\http.php y crear el archivo upload\include\api.users.php que son los 2 archivos necesarios para el funcionamiento de esta API

Una vez tengas Osticket funcional y configurado sera necesario:

Iniciar sesion como un agente Osticket.
Ir al panel de administracion o admin panel
Ir al apartado Manage>API
Creamos una nueva API key
Sera necesario que ingresemos la direccion IP donde se encuentra alojandose nuestra aplicacion, ademas daremos click en las casillas donde permitiremos a la API key generar JSON, XML e EMAIL
Sera necesario que guardemos esta API para despues usarla ya sea como un 'parametro' o como un 'header' para hacer llamados a nuestra API.
Ahora para hacer un llamado a la API sera necesario que tengamos ya un entorno de desarrollo configurado para esto o podria ser utilizado una aplicacion para pruebas (por ejemplo PostMan)

Para hacer un llamado a la API sera necesario hacer un POST hacia la direccion: http://dominio-aplicacion/api/users.json\xml\email
Por ejemplo si alojas tu aplicacion utilizando XAMPP y quieres utilizar un formato json sera necesario utilizar una direccion asi: http://dominio-aplicacion/osticket/upload/api/users.json
Finalmente deberemos ingresar los datos necesarios para la creacion de usuarios, en este caso, en un formato json
``` json
{ 
    "email": "prueba16@ejemplo.com",
    "full_name": "prueba16",
    "phone": "123456789X686",
    "timezone": "America/Los_Angeles",
    "password": "123456789",
    "confirm_password": "123456789"
}
```
***Nota*** La X en telefono es para agregar la extension del telefono, en este caso 686 son la extension del telefono 123456789
