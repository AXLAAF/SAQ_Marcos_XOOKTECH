# Proceso de Despliegue — XookTech

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 07 |
| Proceso | Transición a Entornos de Producción (Gestión de Liberaciones) |
| Estándar de referencia | ISO/IEC 12207 6.4.7 (Proceso de Liberación de Software) |
| Versión | 1.0 |
| Fecha | 2026-05-24 |
| Responsable del proceso | Líder de Desarrollo e Implementación |

---

## 2. Propósito
> Derivado de ISO/IEC 12207.
> Este proceso tiene como propósito empaquetar, verificar y transicionar de forma segura y controlada los módulos de software a los entornos de servidores virtuales privados (VPS) de producción, garantizando la integridad de la configuración, la seguridad de los accesos y la disponibilidad operativa continua del servicio.

## 3. Alcance
*   **Qué cubre:** El aprovisionamiento de dependencias del servidor, la configuración de servidores de aplicaciones (Gunicorn) y proxies inversos (Nginx), la habilitación de cifrado SSL/HTTPS, la instalación de variables del sistema y la ejecución de mecanismos de retorno rápido (rollback) ante contingencias.
*   **Qué NO cubre:** El desarrollo de código fuente de la funcionalidad ni las pruebas unitarias o de integración en el entorno de desarrollo local.

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Líder de Desarrollo e Implementación | Ejecuta el despliegue del sistema en el servidor virtual de producción, configura los archivos de servicio de administración (Systemd) y gestiona los certificados SSL. |
| Analista de Control y Cambios | Revisa y aprueba la integración del código fuente en la rama principal (`main`) antes de autorizar el pase a producción. |
| Administrador de Sistemas SQA | Monitorea la estabilidad y el rendimiento operacional del servidor post-despliegue. |

## 5. Entradas
| Entrada | Origen | Formato actual |
|---|---|---|
| Código fuente verificado | Proceso de Codificación (04) | Rama de repositorio Git |
| Archivos de dependencias (`requirements.txt`) | Proceso de Codificación (04) | Archivo de texto plano |
| Parámetros de entorno del servidor | Gestión de Proyecto | Compartidos de palabra o mediante chats informales |

## 6. Salidas (Artefactos)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Aplicación activa en producción | Usuarios Finales / Clientes | Sistema web expuesto en internet |
| Archivo de servicio de administración | Infraestructura Servidor | Fichero local en `/etc/systemd/system/` |
| Certificado SSL HTTPS | Infraestructura de Seguridad | Certificado web Let's Encrypt |

## 7. Pasos del Proceso
Cómo se hace hoy en la empresa

1.  **Aprovisionamiento manual de dependencias:** Las librerías y dependencias del sistema se instalan directamente en el entorno global del servidor VPS sin aislamiento virtual, lo que provoca conflictos de versiones con otros servicios preexistentes.
2.  **Ejecución insegura de la aplicación:** La aplicación se pone en marcha utilizando directamente el servidor de desarrollo embebido integrado, el cual carece de la robustez, concurrencia y seguridad necesarias para un entorno productivo.
3.  **Exposición directa de puertos:** El puerto de desarrollo se expone directamente a internet sin Nginx como proxy inverso, dejando al servidor vulnerable y sin cifrado de seguridad SSL (HTTP simple).
4.  **Despliegue sin plan de contingencia (Rollback):** Ante cualquier fallo crítico en el despliegue, la aplicación queda interrumpida (inactiva) y se procede a depurar el código directamente en el servidor de producción a contrarreloj.

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| SSH directo | Acceso directo de consola al servidor VPS de producción |
| Entorno de ejecución global | Ejecución directa de dependencias de la aplicación |

## 9. Problemas y Hallazgos Identificados
Esta sección detalla las no conformidades con respecto a la calidad y robustez de infraestructura según estándares.

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | Instalación manual y global de librerías sin entornos aislados. | SWEBOK v4 Cap. 10 / Reproducibilidad |
| **H-02** | Ejecución de la aplicación con servidor de desarrollo embebido. | ISO 12207 §6.4.7 (proceso de liberación de software) |
| **H-03** | Exposición directa del puerto local a internet sin proxy inverso (Nginx) ni cifrado HTTPS. | Galin (2004) Control de Infraestructura |
| **H-04** | Ausencia de pruebas de humo (Smoke Tests) automatizadas y plan de retorno rápido (rollback) atómico ante incidentes. | IEEE 12207 (Release & Deployment Management) |

## 10. Métricas Actuales
*   **Estado de las métricas:** El proceso de despliegue no cuenta actualmente con indicadores formales ni métricas definidas.
*   **Diagnóstico:** No se mide el tiempo de inactividad (downtime) del sistema, la frecuencia de fallos de despliegue ni la cobertura de pruebas de humo (Smoke Tests), dificultando el aseguramiento de la disponibilidad exigido por el cliente.
