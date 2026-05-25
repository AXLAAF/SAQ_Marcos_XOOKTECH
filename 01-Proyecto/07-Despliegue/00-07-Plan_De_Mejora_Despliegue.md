# Plan de Mejora — Despliegue en Producción

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Transición a Entornos de Producción (Gestión de Liberaciones) |
| Documento base | [00-07-Documentacion_Despliegue.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/07-Despliegue/00-07-Documentacion_Despliegue.md) |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 3.0 |
| Fecha | 2026-05-24 |

---

## 2. Objetivo de la Mejora
Establecer un proceso de transición a producción seguro, robusto y estructurado para XookTech. El plan busca aislar los entornos de ejecución, utilizar servidores de aplicaciones de grado industrial, proteger el canal mediante cifrado HTTPS, y definir pruebas de humo y planes de retorno rápido (rollback) automáticos para garantizar una alta disponibilidad de cara al usuario final.

## Tipo de intervención
☒ Mejora de proceso existente  
☐ Implantación de proceso inexistente

---

## 3. Resumen de Hallazg| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | Instalación manual y global de dependencias en el servidor. | **M-01** Aislamiento de entornos virtuales y control exacto de dependencias. |
| **H-02** | Ejecución de la aplicación con servidor de desarrollo embebido. | **M-02** Configuración de servidor de aplicaciones industrial Gunicorn bajo Systemd. |
| **H-03** | Exposición directa de puerto local a internet sin cifrado HTTPS. | **M-03** Implementación de Proxy Inverso Nginx y Certificados SSL. |
| **H-04** | Ausencia de Smoke Tests y plan de Rollback ante fallos críticos. | **M-04** Despliegue seguro con pruebas de humo y plan de retorno rápido automático. |

---

## 4. Acciones de Mejora

| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Aislamiento de entornos virtuales y control de dependencias | H-01 | Líder de Desarrollo | Alta |
| **M-02** | Configuración de servidor de aplicaciones Gunicorn bajo Systemd | H-02 | Líder de Desarrollo | Alta |
| **M-03** | Implementación de Proxy Inverso Nginx y Certificados SSL con Certbot | H-03 | Líder de Desarrollo | Alta |
| **M-04** | Despliegue seguro con pruebas de humo y plan de retorno rápido automático | H-04 | Líder de Desarrollo | Alta |

---

### M-01 — Aislamiento de entornos virtuales y control de dependencias
*   **Situación actual:** Las dependencias se instalan manualmente de manera global en el servidor virtual privado (VPS), arriesgando conflictos lógicos graves (H-01).
*   **Situación propuesta:** Uso obligatorio de un entorno virtual aislado exclusivo para la aplicación en la ruta `/var/www/aplicacion/env`. Congelación exacta de versiones en `requirements.txt`.
*   **Justificación:** SWEBOK v4 y las mejores prácticas de SQA promueven la reproducibilidad de los entornos de ejecución para evitar fallos inesperados de portabilidad.
*   **Artefacto asociado:** [PLT-FOR_Configuracion_Entorno.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/07-Despliegue/Plantillas/Formatos/PLT-FOR_Configuracion_Entorno.md)
*   **Evidencia de cumplimiento:** Directorio de entorno virtual `env` activo en el VPS e instalación exitosa de librerías congeladas.

---

### M-02 — Configuración de servidor de aplicaciones Gunicorn bajo Systemd
*   **Situación actual:** Se ejecuta la aplicación utilizando directamente el servidor embebido de desarrollo, lo cual carece de concurrencia y es inseguro (H-02).
*   **Situación propuesta:** Adoptar el servidor de aplicaciones Gunicorn (WSGI), definiendo hilos de ejecución según la fórmula de procesamiento del VPS (`2n + 1`) y creando un servicio de Systemd para asegurar el auto-reinicio continuo ante caídas del sistema.
*   **Justificación:** El estándar ISO/IEC 12207 establece que la transición de software debe garantizar la resiliencia y la protección ante fallos operativos.
*   **Artefacto asociado:** N/A (configuración del sistema operativo del servidor)
*   **Evidencia de cumplimiento:** Archivo de servicio `/etc/systemd/system/web.service` cargado y configurado en estado de ejecución activo (`active/running`).

---

### M-03 — Implementación de Proxy Inverso Nginx y Certificados SSL con Certbot
*   **Situación actual:** El puerto local de la aplicación está expuesto a internet sin proxy inverso ni cifrado de seguridad SSL (H-03).
*   **Situación propuesta:** Configurar Nginx para escuchar peticiones en puerto 80/443, redirigiendo internamente a Gunicorn y despachando archivos estáticos de forma optimizada. Instalación de Certbot para HTTPS.
*   **Justificación:** Daniel Galin (2004) señala que la seguridad de la infraestructura y el control de accesos externos son elementos de prevención de errores obligatorios en SQA.
*   **Artefacto asociado:** [PLT-REG_Entornos_Servidores.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/07-Despliegue/Plantillas/Registros/PLT-REG_Entornos_Servidores.md)
*   **Evidencia de cumplimiento:** Archivo de bloque de servidor en `/etc/nginx/sites-enabled/web` habilitado y certificado SSL vigente verificado por el navegador.

---

### M-04 — Despliegue seguro con pruebas de humo y plan de retorno rápido automático
*   **Situación actual:** En caso de fallar el despliegue, el sistema colapsa indefinidamente sin un plan de contingencia (H-04).
*   **Situación propuesta:** Adoptar una estrategia de despliegue seguro. Al realizar el pase a producción, se ejecutan de inmediato "pruebas de humo" (Smoke Tests) automatizadas que validan que los endpoints críticos respondan correctamente. Si fallan, se realiza un retorno rápido (rollback) automático al último tag de control estable en Git.
*   **Justificación:** IEEE 12207 (Release and Deployment Management) exige la validación formal post-despliegue mediante pruebas de verificación rápida y el aseguramiento del plan de retorno rápido ante incidentes.
*   **Artefacto asociado:** [PLT-REG_Incidentes_Produccion.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/07-Despliegue/Plantillas/Registros/PLT-REG_Incidentes_Produccion.md), [PLT-FOR_Plan_Smoke_Tests.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/07-Despliegue/Plantillas/Formatos/PLT-FOR_Plan_Smoke_Tests.md) y [CHK-Verificacion_Despliegue.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/07-Despliegue/Checklists/CHK-Verificacion_Despliegue.md)
*   **Evidencia de cumplimiento:** Registros de ejecución de Smoke Tests en la consola de despliegue y checklists de despliegue firmados digitalmente.�n de Smoke Tests en la consola de despliegue y checklists de despliegue firmados digitalmente.

---

## 5. Limitaciones del Plan
*   **Restricciones de hardware del VPS:** CPU o memoria RAM deficientes en el servidor virtual que limiten la capacidad de workers concurrentes de Gunicorn.
*   **Accesibilidad de autoridades certificadoras:** Fallos globales en la red Let's Encrypt que impidan generar o renovar certificados en el momento del despliegue.
*   **Evolución destructiva de datos:** Cambios de base de datos que destruyan registros preexistentes lógicamente no pueden revertirse mediante un simple retorno de código (rollback) en caliente, requiriendo restauración lenta de respaldos.
