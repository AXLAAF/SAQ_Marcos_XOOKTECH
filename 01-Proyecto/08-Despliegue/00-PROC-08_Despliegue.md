# Proceso de Despliegue en Producción -- XookTech
**Responsable:** Líder de Desarrollo e Implementación
**Entradas:** Código Fuente Terminado y Paquetes de Software
**Salidas:** Sistema Desplegado y Guía de Operación

**Área de proceso:** 08-Despliegue
**Nombre del proceso:** Transición a Entornos Productivos (Release Management)
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

> **Antecedente**: Basado en las auditorías de infraestructura previas, se identificó la necesidad de estandarizar el despliegue para evitar discrepancias entre los entornos de desarrollo local y el VPS de producción. Este proceso define el pipeline de transición bajo el estándar IEEE 12207 para garantizar la disponibilidad y seguridad del sistema.

---

## Proceso

### 1. Preparación del Entorno Servidor (Provisioning)

**Actualmente:**
- Las dependencias se instalan manualmente en el servidor sin un registro de versiones exacto.

**NT-1:** La falta de un entorno aislado puede causar conflictos con otros servicios del VPS. SWEBOK v4 recomienda la reproducibilidad de entornos. Se propone el uso de entornos virtuales (`venv`) y congelación de dependencias.

**Propuesta:**
1.  **Aislamiento**: Crear un entorno virtual dedicado en la ruta `/var/www/visualizador-marcos/env`.
2.  **Sincronización**: Ejecutar `pip install -r requirements.txt` asegurando que todas las librerías OpenCV y Flask coincidan con la versión probada en el proceso 05.
3.  **Configuración**: Cargar las variables de entorno (.env) que contienen las rutas al [[03-Diseño/01-Ingenieria_Arquitectura/03-STD-06_Modelo_Datos|catálogo lógico]] y las claves de la API.

---

### 2. Configuración del Servidor de Aplicaciones (Gunicorn)

**Actualmente:**
- El sistema se ejecutaba directamente con el servidor de desarrollo de Flask (`app.run`), lo cual no es seguro ni eficiente para producción.

**NT-2:** El servidor embebido de Flask no soporta múltiples peticiones concurrentes de forma robusta. Se propone el uso de **Gunicorn** como servidor de aplicaciones (WSGI).

**Propuesta:**
1.  **Configuración de Workers**: Definir el número de hilos según el número de núcleos del VPS (Fórmula: 2n + 1).
2.  **Systemd**: Crear un archivo de servicio en `/etc/systemd/system/marcos.service` para que la aplicación se inicie automáticamente tras un reinicio del servidor.
3.  **Monitoreo**: Configurar los logs de errores en `/var/log/marcos/error.log` para auditoría técnica.

---

### 3. Configuración del Proxy Inverso (Nginx)

**Actualmente:**
- El puerto 5000 estaba expuesto directamente a internet, lo cual es una vulnerabilidad de seguridad.

**NT-3:** La exposición directa de puertos de la aplicación es una práctica de alto riesgo. Se propone **Nginx** como capa de seguridad y manejo de archivos estáticos.

**Propuesta:**
1.  **Proxy Pass**: Configurar Nginx para que escuche en el puerto 80/443 y redirija las peticiones internas al puerto 5000 de Gunicorn.
2.  **Optimización**: Nginx servirá directamente las imágenes de la carpeta `static/assets/`, descargando la tarea del servidor Flask y mejorando el tiempo de respuesta.
3.  **Seguridad SSL**: Implementar Certbot (Let's Encrypt) para habilitar HTTPS en todo el dominio.

---

### 4. Ejecución del Despliegue y Rollback

**Actualmente:**
- Ante un error en producción, el sistema queda fuera de línea hasta que se corrige el código manualmente.

**NT-4:** La falta de un plan de contingencia anula el aseguramiento de la disponibilidad. Se propone la estrategia de "Despliegue Atómico".

**Propuesta:**
1.  **Pull de Rama Main**: Solo se despliega código que ha pasado la revisión del **Analista de Control**.
2.  **Smoke Tests**: Tras el reinicio del servicio, se ejecuta un script de prueba rápida para validar que la API responde.
3.  **Rollback**: Si los Smoke Tests fallan, se realiza un `git checkout` a la versión anterior (tag estable) de forma inmediata, minimizando el tiempo de inactividad (Downtime).

---

## Artefactos Producidos (Documentos de Despliegue)

| ID | Artefacto | Propósito | Ubicación |
| :--- | :--- | :--- | :--- |
| **CL-08-01** | Checklist de Despliegue | Lista de verificación final antes de pasar a "En Vivo". | [[08-Despliegue/Documentos_Apoyo/02-Formatos/CL-08-01_Verificacion_Despliegue|CL-08-01]] |
| **REG-08-01** | Registro de Entornos | Documentar IP, puertos y versiones del VPS. | [[08-Despliegue/Documentos_Apoyo/01-Registros/REG-08-01_Entornos_Servidores|REG-08-01]] |
| **FOR-08-01** | Configuración de Proyecto | Plantilla de variables `.env` y configuraciones Nginx. | [[08-Despliegue/Documentos_Apoyo/02-Formatos/FOR-08-01_Configuracion_Proyecto|FOR-08-01]] |

---

## Referencias
- **SWEBOK v4**: Knowledge Area 10 - Software Engineering Process.
- **IEEE 12207**: Processes for Software Configuration Management and Release.
- **Galin (2004)**: Software Quality Assurance - "The infrastructure for error prevention".