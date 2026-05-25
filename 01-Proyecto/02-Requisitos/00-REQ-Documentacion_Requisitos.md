# Proceso de Requisitos de Software — XookTech

**Responsable:** Analista de Requerimientos  
**Entradas:** Solicitudes del cliente y Contrato de Desarrollo.  
**Salidas:** Diagnóstico del proceso actual, análisis de brechas y listado de requisitos.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 02 |
| Proceso | Especificación y Gestión de Requisitos de Software |
| Estándar de referencia | ISO/IEC 12207:2017 §6.4.1 (Proceso de definición de requisitos de negocio) |
| Versión | 1.0 |
| Fecha | 2026-05-24 |
| Responsable del proceso | Analista de Requerimientos |

---

## 2. Propósito
> Derivado de ISO/IEC 12207.
> Este proceso tiene como propósito definir los requisitos para un sistema o servicio de software capaz de satisfacer las necesidades operativas de la organización y del cliente en su contexto de negocio, proveyendo una base confiable, verificable y trazable para la ingeniería de software posterior.

## 3. Alcance
* **Qué cubre:** Captura inicial de necesidades con el Product Owner (PO), modelado preliminar en lenguaje natural, definición de reglas de negocio y el control físico de cambios en Obsidian.
* **Qué NO cubre:** Diseño lógico y físico del sistema (Fase 03), codificación de funcionalidades (Fase 04), pruebas unitarias o de integración (Fase 05), ni el despliegue final a producción.

---

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Requerimientos | Captura las necesidades, redacta los requisitos, coordina las sesiones de validación con el PO y resguarda la matriz de trazabilidad. |
| Analista de Control y Cambios | Audita de forma independiente los requerimientos, aprueba solicitudes de cambio y firma el registro de calidad SQA. |
| Product Owner (PO) | Provee los insumos de negocio, aprueba la especificación técnica de requisitos y autoriza los cambios de alcance. |

---

## 5. Entradas
| Entrada | Origen | Formato actual |
|---|---|---|
| Solicitudes informales | Product Owner | Mensajes sueltos en chats de WhatsApp o acuerdos verbales en llamadas sin acta. |
| Contrato de Desarrollo | Línea Base Original | Archivo digital guardado de forma desorganizada en carpetas del equipo. |
| Solicitudes de cambio | Product Owner | Indicaciones directas por mensajería instantánea sin folio ni análisis de impacto. |

---

## 6. Salidas (Artefactos)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Requisitos del Sistema | Línea Base del SGC | Fichas de notas de texto sueltas mezcladas entre aprobados y pendientes en Obsidian. |
| Matriz de Trazabilidad | Ingeniería de Requisitos | Inexistente. No se cuenta con un mapeo sistemático de enlaces bidireccionales. |
| Registro de Calidad SQA | Aseguramiento de Calidad | Inexistente. Revisiones subjetivas sin soporte documental formal. |

---

## 7. Pasos del Proceso
Cómo se hace hoy en la empresa

1. **Recepción informal:** El PO le comunica ideas y necesidades al equipo de forma verbal o por chat, sin agendas ni actas previas.
2. **Sin folio:** La solicitud se queda en la bandeja de entrada personal, sin registrarse de forma centralizada en el vault de Obsidian.
3. **Redacción de notas libres:** Se escriben párrafos simples descriptivos en lenguaje natural, sin plantillas estandarizadas.
4. **Especificación vaga:** No se establecen límites de archivos, formatos soportados ni restricciones claras, impidiendo diseñar pruebas objetivas.
5. **Programación directa:** Se inicia la programación en Flask y OpenCV sin someter la especificación a revisión formal ni obtener la firma del PO.
6. **Falta de control físico:** Las fichas se resguardan en una carpeta común, mezclando requisitos aprobados y en borrador.
7. **Desconexión de trazabilidad:** No hay un mapeo formal hacia los diagramas de diseño ni a los casos de prueba de calidad.

---

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| WhatsApp / Google Meet | Comunicación y reuniones informales de levantamiento de necesidades sin actas. |
| Obsidian local | Notas de texto desordenadas sin plantillas ni separación física. |
| Correo electrónico | Envío esporádico de archivos de requerimientos preliminares. |

---

## 9. Problemas y Hallazgos Identificados
Esta sección es el núcleo del diagnóstico. Identifica las brechas contra estándares reconocidos.

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | La asignación y captura de requerimientos es informal (WhatsApp) y no deja evidencia. | ISO 12207 §6.4.1.3 / SWEBOK v4 Cap. 2 |
| **H-02** | Ausencia de folios de entrada y registro único de la necesidad de negocio. | ISO 12207 §6.4.1.2 |
| **H-03** | Redacción técnica ambigua en lenguaje natural libre sin límites ni cotas numéricas. | SWEBOK v4 Cap. 2 (Verificabilidad) |
| **H-04** | Inicio de la programación de Flask/OpenCV sin contar con la validación formal escrita del PO. | Daniel Galin 2004 (Calidad Contractual) |
| **H-05** | Mezcla física de archivos pendientes y aprobados en carpetas desorganizadas. | CMMI-DEV v2.0 CM SP 1.1 (Líneas Base) |
| **H-06** | Inexistencia de trazabilidad bidireccional entre requerimientos, diseño y pruebas. | CMMI-DEV v2.0 REQM SP 1.4 |
| **H-07** | Ausencia de auditorías de SQA independientes y de registros de calidad formales. | CMMI-DEV v2.0 PPQA SP 1.1 / IEEE Std 830 |

---

## 10. Métricas Actuales
* **Estado de las métricas:** El proceso de requisitos no cuenta actualmente con ninguna métrica definida para medir la estabilidad, trazabilidad ni calidad de los requisitos.
* **Diagnóstico:** La falta de métricas impide evaluar el rendimiento del proceso, la densidad de defectos de requerimiento y planificar acciones de mejora basadas en datos (CMMI Nivel 2).
