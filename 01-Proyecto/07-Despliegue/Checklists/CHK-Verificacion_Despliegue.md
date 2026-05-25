# [CHK-Verificacion_Despliegue] Checklist de Calidad — Verificación de Despliegue

## Metadatos de la Revisión
| Campo | Valor |
|---|---|
| Proyecto | |
| Servidor VPS | IP / Dominio |
| Versión del Tag (Git) | |
| Revisor / Jefe de Equipo | |
| Fecha de revisión | |
| Resultado general | ✅ Aprobado / ❌ Rechazado |

---

## Instrucciones
Marcar cada ítem como:
- ✅ Cumple
- ❌ No cumple
- N/A No aplica al proyecto

No está permitida la liberación en vivo en producción si existe cualquier ítem obligatorio marcado con ❌.

---

## 1. Fase de Preparación (Pre-Despliegue)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| PR-01 | El código a desplegar reside en la rama `main` y cuenta con la aprobación de control de cambios. | | |
| PR-02 | El entorno virtual de Python (`venv`) está configurado y aislado en el servidor. | | |
| PR-03 | Se generó un backup completo de la base de datos de producción antes del pase. | | |
| PR-04 | Las variables de entorno en el VPS están actualizadas con base en el archivo `.env`. | | |

*Referencia: SWEBOK v4 Cap. 10 / Reproducibilidad y portabilidad*

---

## 2. Fase de Ejecución y Configuración

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| EJ-01 | Las dependencias de `requirements.txt` se instalaron sin fallos o advertencias de compilación. | | |
| EJ-02 | Gunicorn está ejecutándose bajo Systemd como un servicio auto-recuperable (`marcos.service`). | | |
| EJ-03 | Nginx actúa como proxy inverso en puerto 80/443, redirigiendo al puerto interno de la aplicación. | | |
| EJ-04 | Los certificados SSL Let's Encrypt están activos e implementan HTTPS obligatorio. | | |
| EJ-05 | Los directorios de almacenamiento de archivos o subidas tienen permisos seguros restringidos. | | |

*Referencia: ISO/IEC 12207 §6.4.7 (Software Release Process) / Galin (2004)*

---

## 3. Fase de Validación en Vivo (Post-Despliegue)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| PV-01 | Se ejecutaron Smoke Tests (pruebas rápidas de endpoints críticos de la API) de forma exitosa. | | |
| PV-02 | El portal web es accesible externamente a través del dominio y responde en menos de 2 segundos. | | |
| PV-03 | Los archivos de logs en `/var/log/marcos/error.log` no muestran excepciones ni errores fatales de Flask. | | |

*Referencia: IEEE 12207 (Release and Deployment Verification)*

---

## 4. Plan de Rollback (Contingencia)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| RB-01 | Se especificó formalmente el comando de retorno rápido de versión (ej: `git checkout <tag_anterior>`). | | |
| RB-02 | El programador responsable del Rollback está en guardia y definido por escrito. | | |

*Referencia: ITIL v4 Change Control / Aseguramiento de Disponibilidad*

---

## Resumen de Hallazgos SQA

| ID Ítem | Observación técnica | Acción correctiva requerida |
|---|---|---|
| | | |

## Decisión de Pase a Producción

| Resultado | Criterio |
|---|---|
| ✅ Aprobado | 0 ítems en ❌ |
| ❌ Rechazado | 1 o más ítems en ❌ (Debe suspenderse el despliegue) |

**Decisión:** 
**Firmado por:**
**Fecha:**
