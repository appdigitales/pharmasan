## Prueba
Realizar una aplicación en Laravel que permita:

● Inicio de sesión

● Registro de usuarios

● Actualización de usuarios

● Búsqueda de usuarios

● Eliminación de usuarios

● El inicio de sesión debe permitir, que el logueo se realice como rol administrador
o vendedor.

● El rol administrador debe poder realizar toda la administración de usuarios
(creación, actualización y eliminación) y clientes (creación, actualización y
eliminación).

● El rol vendedor debe poder realizar la creación, actualización y eliminación de
clientes (nombre, documento, correo, dirección)

● El rol de administrador y vendedor agregar un módulo de reportes donde liste
los artículos de medicamentos (Paginados) del Invima anexos en el correo.

● Que pueda realizar descarga JSON los registros en formato (CSV for Excel)

● Cerrar sesión

● Validaciones de permisos por rol.

## Features

- Laravel 7
- Vue + VueRouter + Vuex + VueI18n + ESlint
- Pages with dynamic import and custom layouts
- Login, register, email verification and password reset
- Authentication with JWT
- Socialite integration
- Bootstrap 4 + Font Awesome 5

## Installation LARAGON
```bash
cd laragon/www/
git clone https://github.com/hammer92/pharmasan.git

compose install
npm install

copiar .env.example como .env

configurar datos de conexion y crear base de datos pharmasan

php artisan migrate
php artisan db:seed 

si hay errores de memoria en el comando  db:seed ir al archivo 
php.ini y aumentar el valos de memory_limit=10240M

npm run dev

```

## Installation Docker
```bash
git clone https://github.com/hammer92/pharmasan.git

sudo chown -R $USER:$USER ~/pharmasan

docker-compose build

docker-compose up -d

docker-compose exec app compose install
docker-compose exec vueserver npm install


```

## Crear Usuario MySQL Docker
```bash
docker-compose exec db bash

mysql -u root -p

GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'your_laravel_db_password';
FLUSH PRIVILEGES;
EXIT;
exit

docker-compose exec app php artisan migrate

docker-compose exec app php artisan db:seed  

```
