# FOR-08-01: Configuración de Proyecto — XookTech

**Proceso relacionado:** [[00-PROC-08_Despliegue]]
**Responsable de mantenerlo:** El programador que configure el entorno.
**Instrucciones generales:** Utilice este documento para describir los requisitos de entorno de cualquier proyecto. No incluya valores sensibles reales aquí.

## 1. Requisitos de Software
- **Lenguaje/Runtime:** (Ej: Node.js v20, PHP 8.2)
- **Base de Datos:** (Ej: MySQL 8.0, PostgreSQL 15)
- **Servicios Externos:** (Ej: Redis, RabbitMQ, S3)

## 2. Variables de Entorno (.env)
Enumere las variables necesarias para que el sistema funcione:

| Variable    | Descripción                             | ¿Cambia en Prod? |
| :---------- | :-------------------------------------- | :--------------- |
| `APP_KEY`   | Llave de cifrado de la aplicación       | Sí               |
| `DB_HOST`   | Dirección del servidor de base de datos | Sí               |
| `MAIL_HOST` | Servidor de correos                     | No               |

## 3. Comandos de Despliegue
Liste los comandos necesarios para poner en marcha el proyecto:
1. `npm install` o `composer install`
2. `php artisan migrate`
3. `systemctl restart xooktech-service`

## 4. Notas de Infraestructura
- (Describa aquí si el proyecto requiere configuraciones especiales en Nginx, Apache o Cronjobs).
