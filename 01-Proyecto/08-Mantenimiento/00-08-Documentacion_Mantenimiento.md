# Proceso de Soporte y Mantenimiento — XookTech

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 08 |
| Proceso | Soporte técnico y mantenimiento del sistema |
| Estándar de referencia | ISO/IEC 12207 §6.4.10 (Proceso de Mantenimiento de Software) / ISO/IEC 14764 |
| Versión | 1.0 |
| Fecha | 2026-05-24 |
| Responsable del proceso | Analista de Gobernanza y Diseño |

---

## 2. Propósito
> Derivado de ISO/IEC 12207.
> Este proceso tiene como propósito dar soporte continuo post-entrega al sistema, corrigiendo fallas lógicas o de infraestructura reportadas por el cliente, adaptando el software a variaciones del entorno operativo, previniendo la degradación del rendimiento e implementando mejoras autorizadas bajo controles rigurosos de calidad.

## 3. Alcance
*   **Qué cubre:** La recepción y bitácora de reportes de error (Correctivo) y peticiones de cambio (Evolutivo/Adaptativo), el análisis de impacto técnico en los módulos de la aplicación Flask y base de datos, la estimación del esfuerzo en horas/costo, el desarrollo aislado en ramas de corrección urgente, la ejecución de pruebas de regresión del Plan Maestro y la actualización de la Línea Base.
*   **Qué NO cubre:** El desarrollo de la primera versión del sistema o sus fases de construcción principales pre-producción.

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Gobernanza y Diseño | Recibe y registra los reportes de incidentes, clasifica su severidad, realiza el análisis de impacto técnico en el diseño del sistema y actualiza el Dashboard de Calidad. |
| Líder de Desarrollo e Implementación | Estima el esfuerzo requerido, codifica las correcciones en ramas de corrección urgente aisladas e integra los cambios certificados tras las pruebas. |
| Analista de Verificación y Pruebas | Re-ejecuta de inmediato los casos de prueba de regresión pertinentes sobre el ambiente local/staging. |

## 5. Entradas
| Entrada | Origen | Formato actual |
|---|---|---|
| Reportes de error / Solicitudes de cambio | Clientes o Product Owner | Conversaciones verbales, llamadas no programadas o chats informales |
| Plan de Pruebas de Regresión | Proceso de Pruebas (06) | Documento maestro sin uso constante en soporte |
| Diseño lógicos del sistema | Proceso de Diseño (03) | Plan de arquitectura estático |

## 6. Salidas (Artefactos)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Correcciones en producción | Entornos de producción | Correcciones integradas a la rama principal |
| Registro de incidentes | Bitácora de Soporte | Hojas informales o chats archivados |
| Cotización del cambio formal | Propietario del producto (Product Owner) | Presupuestos informales verbales |

## 7. Pasos del Proceso
Cómo se hace hoy en la empresa

1.  **Recepción informal de incidencias:** Los usuarios reportan de palabra, por chats dispersos o llamadas directas. No existe una bitácora única de incidentes, lo que causa que los problemas críticos de Flask u OpenCV no se prioricen de manera oportuna.
2.  **Parche directo en producción:** El equipo de desarrollo modifica o "parchea" el código fuente directamente en producción sin realizar previamente un análisis de impacto de dependencias y sin emitir una cotización de horas técnica.
3.  **Integración sin pruebas de regresión:** Los cambios se inyectan en caliente sobre la rama principal sin re-ejecutar pruebas lógicas completas, asumiendo empíricamente que la solución es infalible y rompiendo colateralmente otros módulos estables.
4.  **Cierre documental inexistente:** Una vez realizada la corrección, no se actualizan los diagramas técnicos de diseño de base de datos ni el Tablero (Dashboard) de Calidad de la empresa, perdiéndose las lecciones aprendidas de soporte.

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| Chats / Correo electrónico | Recepción dispersa y desestructurada de fallos lógicos |
| Consola del Servidor | Modificación y subida de archivos directos de código fuente |

## 9. Problemas y Hallazgos Identificados
Esta sección diagnostica formalmente las brechas frente a estándares internacionales de mantenimiento de software.

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | Recepción verbal y desestructurada de fallos sin bitácora única de priorización y categorización. | ISO/IEC 14764 §5.1 / Regan (2002) |
| **H-02** | Modificación del código fuente ("parcheo") en producción sin análisis de impacto ni cotización técnica. | SWEBOK v4 Cap. 4 (Mantenimiento de Software) |
| **H-03** | Aplicación directa de cambios sin re-ejecutar pruebas de regresión integrales del Plan de Pruebas. | Lewis (2009) Pruebas de Regresión |
| **H-04** | Cierre técnico sin actualización de diagramas de arquitectura de base de datos ni métricas de calidad. | CMMI-DEV v2.0 (Gestión de la Configuración) |

## 10. Métricas Actuales
*   **Estado de las métricas:** El proceso de soporte y mantenimiento técnico de XookTech no dispone en la actualidad de métricas definidas.
*   **Diagnóstico:** No se miden el tiempo medio de resolución (MTTR), la tasa de recurrencia de errores en producción, ni el índice de satisfacción del cliente ante solicitudes post-entrega.
