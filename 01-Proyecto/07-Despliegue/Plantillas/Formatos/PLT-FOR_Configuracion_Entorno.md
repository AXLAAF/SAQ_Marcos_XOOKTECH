# [PLT-FOR_Configuracion_Entorno] Configuración del Entorno de Producción

## Metadatos del Documento
| Campo | Valor |
|---|---|
| Proyecto | |
| Proceso | Despliegue (PROC-07) |
| Responsable | Líder de Desarrollo e Implementación |
| Estándar de referencia | ISO/IEC 12207 / SWEBOK v4 |

---

## 1. Requisitos del Entorno (Línea Base de Infraestructura)
*   **Servidor:** Servidor Virtual Privado (VPS) con sistema operativo Linux (Ubuntu Server LTS recomendado).
*   **Servidor de Aplicaciones:** Gunicorn (o servidor de aplicaciones compatible con la tecnología web).
*   **Proxy Inverso y Web:** Nginx.
*   **Seguridad:** Certificados SSL/TLS activos (Let's Encrypt / Certbot).
*   **Base de Datos:** Base de datos activa y configurada (SQL/NoSQL según entorno).

---

## 2. Variables de Entorno (.env.example)
Variables necesarias para inicializar el servidor web de la aplicación. **PROHIBIDO colocar valores confidenciales reales aquí**.

| Variable | Descripción técnica | ¿Es crítica en producción? |
|:---|:---|:---|
| `APP_ENV` | Define el entorno de ejecución (development/production) | Sí |
| `SECRET_KEY` | Llave criptográfica para firmas y sesiones seguras | Sí |
| `PORT` | Puerto de escucha interno para el servidor de aplicaciones | Sí |
| `DATABASE_URL` | URI de conexión a la base de datos de producción | Sí |
| `LOG_LEVEL` | Nivel de detalle del sistema de logs (INFO, WARNING, ERROR) | No |

---

## 3. Comandos Estándar de Instalación y Despliegue en el VPS
1.  **Aislamiento y Preparación del Entorno:**
    ```bash
    # Crear y activar el entorno de ejecución aislado
    virtualenv env
    source env/bin/activate
    ```
2.  **Sincronización de Dependencias:**
    ```bash
    # Instalar dependencias requeridas congeladas
    pip install -r requirements.txt
    ```
3.  **Ejecución con Servidor de Aplicaciones (Gunicorn):**
    ```bash
    # Ejecutar en segundo plano en puerto local con workers concurrentes
    gunicorn --workers 3 --bind 127.0.0.1:5000 app:app
    ```
4.  **Habilitación del Servicio del Sistema (Systemd):**
    ```bash
    # Copiar archivo de servicio y habilitar inicio automático
    sudo cp web.service /etc/systemd/system/
    sudo systemctl daemon-reload
    sudo systemctl enable web.service
    sudo systemctl start web.service
    ```

---

## 4. Historial de Versiones de Plantilla
| Versión | Fecha | Autor | Modificación |
|---|---|---|---|
| 1.0 | 2026-05-24 | Líder de Desarrollo | Creación e implantación inicial como estándar del entorno. |
