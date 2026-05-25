# [PLT-FOR_Plan_Smoke_Tests] Plan de Pruebas de Humo (Smoke Tests)

## Metadatos del Documento
| Campo | Valor |
|---|---|
| Proyecto | |
| Proceso | Despliegue (PROC-07) |
| Responsable | Líder de Desarrollo e Implementación |
| Estándar de referencia | IEEE 12207 / Release & Deployment Verification |

---

## 1. Instrucciones de Uso
*   Este plan define las validaciones mínimas inmediatas que deben ejecutarse tras cada despliegue en el servidor de producción.
*   Si alguno de los Smoke Tests marcados como **Crítico** no se cumple con éxito, se debe suspender la liberación y activar de inmediato el **Plan de Rollback**.

---

## 2. Definición de Pruebas de Humo

| ID | Categoría | Componente a Validar | Descripción de la Validación | Criterio de Éxito | ¿Es Crítico? | Estado (Aprobado/Fallido) |
|:---|:---|:---|:---|:---|:---:|:---:|
| **SMK-01** | Infraestructura | Puerto Nginx (80/443) | Comprobar que Nginx escuche y reciba peticiones externas en los puertos estándar HTTP y HTTPS. | Nginx responde y redirige peticiones. | Sí | |
| **SMK-02** | Proceso | Servicio Systemd | Comprobar que el servicio `web.service` que administra Gunicorn se encuentre en estado `active (running)`. | Comando `systemctl status` muestra el servicio activo. | Sí | |
| **SMK-03** | Conectividad | Endpoint Raíz (`/`) | Realizar una petición HTTP GET al endpoint raíz de la aplicación web y verificar su respuesta. | Retorna código de estado HTTP `200 OK` en menos de 2 segundos. | Sí | |
| **SMK-04** | Integración | Endpoint de Salud (`/health`) | Invocar el endpoint de monitoreo/salud y comprobar la respuesta del estado del servidor. | Retorna JSON con estado `{"status": "healthy"}`. | Sí | |
| **SMK-05** | Persistencia | Conexión a Base de Datos | Invocar un endpoint de lectura del catálogo para asegurar que la base de datos esté activa y responda consultas. | Retorna los registros configurados sin excepciones de base de datos. | Sí | |
| **SMK-06** | Integridad | Logs de error | Inspeccionar los logs del proxy Nginx (`/var/log/nginx/error.log`) y de la aplicación web. | Sin excepciones de código ni fallas fatales de compilación o dependencias. | No | |

---

## 3. Registro de Ejecución y Firmas SQA
*   **Fecha de Ejecución:** DD/MM/AAAA
*   **Hora de Ejecución:** HH:MM
*   **Versión del Despliegue (Tag Git):** vX.Y.Z
*   **Dictamen Final de Smoke Tests:** ✅ APROBADO / ❌ RECHAZADO (Requiere Rollback)

**Responsable de Pruebas (Líder Desarrollo):** _____________________________  
**Verificado y Autorizado (Analista Control):** _____________________________  

---

## 4. Historial de Versiones de Plantilla
| Versión | Fecha | Autor | Modificación |
|---|---|---|---|
| 1.0 | 2026-05-24 | Líder de Desarrollo | Creación e implantación inicial como compuerta de calidad post-despliegue. |
