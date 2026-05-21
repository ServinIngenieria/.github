# Información General del Portal

## Tecnologías Utilizadas
- **Frontend:** Angular
- **Backend:** Laravel
- **Base de Datos:** MySQL (Dockerizado)
- **Infraestructura:** Linode VPS

## Pasos para subir cambios a producción
#### 🔧 Backend (Laravel)

1. Subir los cambios al repositorio `app_laravel` en GitHub.
2. Acceder al servidor Linode vía consola.
3. Ir a la carpeta del proyecto: `/var/www/backend_backoffice_repo/app_laravel/`
4. Traer los cambios remotos: `git pull origin main`

#### 🎨 Frontend (Angular)
1. Compilar para producción: `ng build --configuration production`
2. Subir los archivos al servidor: `scp -i tu-ruta-a-clave-ssh -r dist\* tu-usuario@tu-ip:/var/www/html/`
> Reemplazar por la ruta a tu clave, usuario e IP de la consola Linode.

## 🖥️ Acceso al Servidor (Linode)

#### Opción 3: CMD/ terminal (SSH)
1. Abrir CMD o una terminal.
2. Conectarse `ssh -i /ruta/a/tu-clave-privada.pem tu-usuario@tu-ip`

#### Opción 2: LISH Console (Web)
1. Ir a `cloud.linode.com`
2. Seleccionar el servidor debian-us-ord-backoffice
3. Hacer clic en Launch LISH Console

#### Opción 3: Putty (SSH)
1. Abrir Putty
2. En `Session → Host Name`, ingresar la IP pública
3. En `Connection → SSH → Auth`, cargar la clave .ppk desde: `C:\Users\INSPECCIONES\.ssh\`
4. Ingresar como usuario `root`

## 🐋 Docker: Comandos útiles
Ruta del proyecto: `/var/www/backend_backoffice_repo/app_laravel/`

#### Reiniciar los contenedores
   - `docker compose down`
   - `docker compose up -d`
#### Acceder al contenedor de base de datos
   - `docker exec -it servin_db bash`
   - `mysql -u root p`
#### Acceder al contenedor del backend Laravel
   - `docker compose exec servin_backend bash`
   
## 🔐 Accesos y Credenciales
⚠️ Las credenciales están almacenadas de forma segura en el archivo `.env` del proyecto Laravel

CLOUD LINODE
- Usuario: `ENV(LINODE_USER)`
- Contraseña: `ENV(LINODE_PASSWORD)`

CONSOLE LINODE
- Usuario: `ENV(LINODE_ROOT_USER)`
- Contraseña: `ENV(LINODE_ROOT_PASSWORD)`

INNOVACION TECNOLÓGICA CORREO
- Usuario: `ENV(MAIL_USER)`
- Contraseña: `ENV(MAIL_PASSWORD)`

GITHUB
- Usuario: `ENV(GITHUB_USER)`
- Contraseña: `ENV(GITHUB_PASSWORD)`

GITHUB ACCESS TOKEN LINODE BACKEND
- Token: `ENV(GITHUB_TOKEN)`

RUTA CLAVE SSH LOCAL
SSH_KEY_PATH=C:\\Users\\INSPECCIONES\\.ssh\\clave-openssh.pem

### BASE DE DATOS DOCKER (LINODE)
- Usuario: `ENV(MYSQL_ROOT_USER)`
- Contraseña: `ENV(MYSQL_ROOT_PASSWORD)`
