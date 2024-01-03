1. Instalar composer cambiando la ruta de xampp a C:\xampp\php\windowsXamppPhp
2. Instalar scoop con el comando:
irm get.scoop.sh -outfile 'install.ps1'
.\install.ps1 -RunAsAdmin [-OtherParameters ...]
I don't care about other parameters and want a one-line command
iex "& {$(irm get.scoop.sh)} -RunAsAdmin"
3.Instalar symfony con comando:
scoop install symfony-cli

4. Creamos nuestro primer proyecto por ejemplo en Documents con: 
PS C:\Users\Admin\Documents> symfony new --webapp holasymfony
**Se puede crear donde se quiera por ejemplo dentro de xampp crear una carpeta que se llame SymfonyProject
Dentro ejecutar el comando: symfony new NombreProyecto --webapp

5. Entramos dentro de la carpeta del proyecto y ejecutamos el server
PS C:\Users\Admin\Documents\holasymfony> symfony server:start

6.Para hacer la conexion a DB debemos modificar el fichero .env y poner:
DATABASE_URL="mysql://root:@127.0.0.1:3306/symfonydb?serverVersion=10.4.28-MariaDB&charset=utf8mb4"
*root(nombre usuario) :password si hubiese y despues de 3306/NombreBD

7. Copiar el archivo php.ini de C:\xampp\php a C:\xampp\php\windowsXamppPhp
8. Comandos php bin/console list (Muestra todas las opciones)

9. Para crear la BD que no existe podemos utilizar el comando:
php bin/console doctrine:database:create

10. Para crear entidades (tablas) se hace con:
php bin/console make:entity
Se configura: poniendo el (nombreTabla, Campos (El Id no hace falta hacerlo), tipo, longitud y si es nulo o no
-Se pone ? para saber el resto de tipos.

11. Realizar Migraciones: usar el comando php bin/console make:migration
12. Cargar las migraciones a BD
php bin/console doctrine:migration:migrate

13. Hacer CRUD: (CONTROLADORES con acciones) poner el comando php bin/console make:crud
**Si da fallo poner el comando: composer require annotation
(Se pone el nombre de la tabla que se quiere hacer el Crud)
El nombre del controlador y oie ultimo el el TEST (en este caso NO)

14. Arrancar servidor con comando: symfony serve

15. Si da fallo en carpeta template-base.html.twig (borrar linea {{ux_controller_link_tags() }}
