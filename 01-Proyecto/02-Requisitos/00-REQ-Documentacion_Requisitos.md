# Documentación del Proceso de Requisitos (As-Is) —XookTech

**Responsable:** Analista de Requerimientos  
**Entradas:** Solicitudes informales y vagas del cliente, propuestas preliminares de la línea base y necesidades empíricas del SGC.  
**Salidas:** Análisis de conformidad y mapeo de actividades as-is, identificación formal de brechas y catálogo de artefactos actuales.  

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
*   **Qué cubre:** La captura inicial de necesidades con el Product Owner (PO), el modelado preliminar en lenguaje natural, la traducción a reglas de negocio técnicas, la aprobación contractual y el control elemental de cambios en Obsidian.
*   **Qué NO cubre:** El diseño lógico y físico del sistema (Fase 03), la codificación de funcionalidades (Fase 04), la automatización de casos de prueba (Fase 05), ni el despliegue a producción.

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Requerimientos | Gestiona la captura, modela los escenarios de aceptación, coordina las sesiones de validación técnica con el PO y resguarda la matriz de trazabilidad. |
| Analista de Control y Cambios | Audita de forma independiente los requerimientos, firma el registro de calidad SQA y aprueba las solicitudes de cambio (CR-XXX). |
| Product Owner (PO) | Provee los insumos de negocio, aprueba por escrito la especificación técnica final de los requisitos y autoriza los cambios de alcance. |

## 5. Entradas (Empíricas / As-Is)
| Entrada | Origen | Formato actual |
|---|---|---|
| Solicitudes informales | Product Owner | Chats dispersos de WhatsApp, llamadas telefónicas o acuerdos verbales sin acta |
| Contrato de Desarrollo | Línea Base Original | Copia digital guardada de manera informal en carpetas comunes |
| Solicitudes de cambio (CR) | Product Owner | Indicaciones al vuelo vía mensajería instantánea sin folio ni análisis de impacto |

## 6. Salidas / Artefactos (Empíricas / As-Is)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Requisitos del Sistema | Línea Base del SGC | Fichas de notas de texto sueltas mezcladas entre aprobados y pendientes |
| Matriz de Trazabilidad RTM | Ingeniería de Requisitos | Inexistente (no se cuenta con un mapeo sistemático de enlaces bidireccionales) |
| Registro de Calidad SQA | SQA | Inexistente (las revisiones son subjetivas y a criterio de cada programador) |

---

## 7. Pasos del Proceso (As-Is / Cómo se hace hoy)

1.  **Recepción informal de solicitudes:** El PO le comunica una idea o necesidad de negocio al equipo de forma verbal o vía mensajería, sin que exista una agenda formal ni Reporte de Junta previo.
2.  **Ausencia de folio y registro único:** La solicitud se queda en la bandeja de chats personales, sin centralizarse en un folio identificable ni nota de entrada en el vault de Obsidian.
3.  **Redacción de notas informales:** Se redacta un párrafo descriptivo corto en lenguaje natural libre, sin inyectar ninguna plantilla estandarizada de especificación técnica.
4.  **Ambigüedad técnica:** No se establecen límites de peso máximo de archivos, formatos soportados, ni cotas de rendimiento, impidiendo que el equipo de pruebas diseñe casos de verificación objetivos.
5.  **Validación ausente con el PO:** Se asume de forma interna que lo comprendido es correcto y se inicia la programación directa en Flask/OpenCV sin someter la especificación técnica detallada a una revisión con el PO.
6.  **Falta de control físico de la Línea Base:** Las fichas técnicas en Obsidian se mantienen en una carpeta común y desorganizada, mezclando requisitos inestables con aprobados y dificultando la visibilidad técnica.
7.  **Desconexión de trazabilidad:** No se cuenta con un mapeo formal hacia los diagramas de diseño ni a los casos de prueba de calidad, perdiéndose la trazabilidad en el ciclo de vida del desarrollo.

---

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| WhatsApp / Google Meet | Comunicación informal y llamadas de levantamiento sin actas técnicas |
| Obsidian local | Notas de texto desordenadas sin segregación ni plantillas formales |
| Correo electrónico | Envío esporádico de archivos de requerimientos preliminares |

---

## 9. Problemas y Hallazgos Identificados (Análisis de Brechas)

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | La asignación y captura de requerimientos es informal (WhatsApp) y no deja evidencia. | ISO 12207 §6.4.1.3 / SWEBOK v4 Cap. 2 |
| **H-02** | Ausencia de folios de entrada y registro único de la necesidad de negocio. | ISO 12207 §6.4.1.2 |
| **H-03** | Redacción técnica ambigua en lenguaje natural libre sin límites ni cotas numéricas. | SWEBOK v4 Cap. 2 (Verificabilidad de Requisitos) |
| **H-04** | Inicio de la programación de Flask/OpenCV sin contar con la validación formal escrita del PO. | Daniel Galin 2004 (Calidad Contractual) |
| **H-05** | Mezcla física de archivos pendientes y aprobados en carpetas desorganizadas. | CMMI-DEV v2.0 CM SP 1.1 (Líneas Base) |
| **H-06** | Inexistencia de trazabilidad bidireccional entre requerimientos, diseño y pruebas. | CMMI-DEV v2.0 REQM SP 1.4 |
| **H-07** | Ausencia de auditorías de SQA independientes y de registros de calidad formales. | CMMI-DEV v2.0 PPQA SP 1.1 / IEEE Std 830 |

---

## 10. Métricas Actuales (As-Is)
*   **Estado de las métricas:** El proceso operativo de requisitos de XookTech no cuenta actualmente con ninguna métrica definida para medir la estabilidad de requisitos, el porcentaje de trazabilidad bidireccional de la línea base, ni el cumplimiento de los estándares de especificación.
*   **Diagnóstico:** La falta de métricas imposibilita la visibilidad del rendimiento y bloquea cualquier iniciativa de mejora continua cuantificable (CMMI-DEV Nivel 2).
