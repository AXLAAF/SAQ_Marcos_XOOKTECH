# Plan de Mejora — Diseño de Software

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Diseño de la Arquitectura y Componentes de Software |
| Documento base | [[00-DIS-Documentacion_Diseño.md]] |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 1.0 |
| Fecha | 2026-05-25 |

---

## 2. Objetivo de la Mejora
Implantar un proceso de diseño de software disciplinado, verificable y repetible en XookTech. El plan busca estructurar la producción obligatoria de un Documento de Descripción de Diseño (SDD) basado en IEEE Std 1016, definir la arquitectura mediante diagramas Mermaid.js, registrar decisiones técnicas justificadas, especificar modelos de datos e interfaces antes de programar, y garantizar la trazabilidad bidireccional mediante la Matriz RTM y auditorías con el checklist oficial de diseño.

## Tipo de intervención
[ ] Mejora de proceso existente  
[X] Implantación de proceso inexistente  

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | No existe una fase de diseño de software formalizada en el ciclo de vida. | **M-01** Implantación del proceso formal de diseño arquitectónico con modelo ETVX. |
| **H-02** | No se produce un Documento de Descripción de Diseño (SDD) que guíe la codificación. | **M-02** Redacción obligatoria del SDD bajo plantilla IEEE Std 1016. |
| **H-03** | Las decisiones tecnológicas y de arquitectura no se documentan ni justifican. | **M-03** Registro formal de decisiones de arquitectura y selección de componentes. |
| **H-04** | No existen diagramas de descomposición lógica, comportamiento ni vista física. | **M-04** Producción obligatoria de diagramas arquitectónicos en Mermaid.js. |
| **H-05** | El modelo de datos y las interfaces de componentes se definen improvisadamente. | **M-05** Especificación formal del modelo de datos e interfaces de componentes. |
| **H-06** | Ausencia de trazabilidad bidireccional entre requisitos aprobados y elementos de diseño. | **M-06** Mapeo obligatorio de elementos de diseño en la Matriz RTM. |
| **H-07** | No existe un checklist de calidad para auditar el diseño antes de codificar. | **M-07** Inspección formal del SDD mediante checklist de verificación con ciclo de rechazo. |

---

## 4. Acciones de Mejora

| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Implantación del proceso formal de diseño arquitectónico con modelo ETVX | H-01 | Analista de Gobernanza y Diseño | Alta |
| **M-02** | Redacción obligatoria del SDD bajo plantilla IEEE Std 1016 | H-02 | Analista de Gobernanza y Diseño | Alta |
| **M-03** | Registro formal de decisiones de arquitectura y selección de componentes | H-03 | Analista de Gobernanza y Diseño | Alta |
| **M-04** | Producción obligatoria de diagramas arquitectónicos en Mermaid.js | H-04 | Analista de Gobernanza y Diseño | Alta |
| **M-05** | Especificación formal del modelo de datos e interfaces de componentes | H-05 | Analista de Gobernanza y Diseño | Alta |
| **M-06** | Mapeo obligatorio de elementos de diseño en la Matriz RTM | H-06 | Analista de Gobernanza y Diseño | Media |
| **M-07** | Inspección formal del SDD mediante checklist de verificación con ciclo de rechazo | H-07 | Revisor SQA | Alta |

---

### M-01 — Implantación del proceso formal de diseño arquitectónico con modelo ETVX
* **Situación actual:** XookTech no cuenta con ninguna fase de diseño de software. La transición de requisitos a codificación es directa e informal (H-01).
* **Situación propuesta:** Se establece como obligatorio un proceso de diseño de software que se ejecute después de la aprobación de requisitos y antes del inicio de la codificación. El proceso se rige por el modelo ETVX: los criterios de entrada exigen requisitos aprobados y firmados; las tareas incluyen la producción del SDD, diagramas y modelo de datos; la salida es el paquete de diseño verificado; y la verificación la realiza el Revisor SQA mediante checklist formal.
* **Justificación:** ISO/IEC 12207 §6.4.4 establece que todo ciclo de vida de software debe incluir un proceso de diseño arquitectónico que transforme los requisitos en una descripción de diseño verificable antes de la implementación.
* **Artefacto asociado:** [[PLT-FOR_Plantilla_SDD.md]]
* **Evidencia de cumplimiento:** Directorio `03-Diseño/` activo en el SGC conteniendo el plan de mejora, el checklist y las plantillas completas del proceso.

---

### M-02 — Redacción obligatoria del SDD bajo plantilla IEEE Std 1016
* **Situación actual:** No se produce ningún documento de diseño que guíe la codificación. Los programadores codifican a partir de instrucciones verbales (H-02).
* **Situación propuesta:** Es obligatorio producir un Documento de Descripción de Diseño de Software (SDD) utilizando la plantilla formal [[PLT-FOR_Plantilla_SDD.md]] antes de iniciar cualquier actividad de codificación. El SDD debe incluir las cuatro vistas arquitectónicas de IEEE Std 1016: descomposición, comportamiento lógico, vista física y vista de datos.
* **Justificación:** IEEE Std 1016-2009 define la estructura mínima de un SDD y establece que la descripción del diseño debe contener múltiples puntos de vista (viewpoints) para garantizar la comprensión completa de la arquitectura.
* **Artefacto asociado:** [[PLT-FOR_Plantilla_SDD.md]]
* **Evidencia de cumplimiento:** SDD completado y almacenado en el SGC con las cuatro vistas arquitectónicas redactadas y verificadas mediante el checklist de diseño.

---

### M-03 — Registro formal de decisiones de arquitectura y selección de componentes
* **Situación actual:** Las decisiones tecnológicas (Flask vs FastAPI, OpenCV vs Pillow, SQLite vs JSON) se toman de manera implícita y no se registran (H-03).
* **Situación propuesta:** Toda decisión de arquitectura relevante debe documentarse en el SDD utilizando el Registro de Decisiones de Arquitectura [[PLT-REG_Decisiones_Arquitectura.md]], detallando: el contexto técnico, las alternativas evaluadas, la justificación de la alternativa elegida y las consecuencias del impacto.
* **Justificación:** CMMI-DEV v2.0 TS SP 1.1 (Selección de Soluciones de Componentes de Producto) establece que se deben evaluar y documentar las alternativas de solución técnica con criterios objetivos antes de comprometerse con una implementación.
* **Artefacto asociado:** [[PLT-REG_Decisiones_Arquitectura.md]]
* **Evidencia de cumplimiento:** Registro de Decisiones de Arquitectura completado con al menos una entrada por cada tecnología crítica del sistema.

---

### M-04 — Producción obligatoria de diagramas arquitectónicos en Mermaid.js
* **Situación actual:** No existen diagramas de componentes, flujos de sistema ni vistas físicas del software (H-04).
* **Situación propuesta:** El Analista de Gobernanza y Diseño debe producir como mínimo tres diagramas técnicos en formato Mermaid.js antes de liberar el paquete de diseño: (1) diagrama de descomposición lógica de componentes, (2) diagrama de secuencia del comportamiento dinámico y (3) diagrama de la estructura física del repositorio. Estos diagramas se integran al SDD utilizando la plantilla [[PLT-FOR_Diagrama_Arquitectura.md]].
* **Justificación:** IEEE Std 1016-2009 establece que la descripción del diseño debe incluir múltiples puntos de vista (viewpoints) modelados mediante notaciones formales para garantizar la comprensión del sistema por todos los interesados.
* **Artefacto asociado:** [[PLT-FOR_Diagrama_Arquitectura.md]]
* **Evidencia de cumplimiento:** Diagramas técnicos en Mermaid.js renderizados e incorporados al SDD y verificados en el checklist de diseño.

---

### M-05 — Especificación formal del modelo de datos e interfaces de componentes
* **Situación actual:** Las tablas de base de datos, esquemas JSON y firmas de funciones se definen ad-hoc durante la codificación (H-05).
* **Situación propuesta:** Antes de iniciar la codificación, el SDD debe contener: (1) el modelo de datos completo con campos, tipos, llaves primarias, relaciones y restricciones, y (2) la especificación de interfaces de software con las signaturas de funciones críticas, parámetros de entrada/salida, tipos de retorno y códigos de respuesta HTTP de cada endpoint.
* **Justificación:** ISO/IEC 12207 §6.4.4 y SWEBOK v4 Cap. 2 (Diseño de Software) establecen que la especificación de interfaces y modelos de datos es un entregable obligatorio del proceso de diseño que previene acoplamientos fuertes e inconsistencias de persistencia.
* **Artefacto asociado:** N/A (secciones integradas directamente en el SDD)
* **Evidencia de cumplimiento:** Secciones de Vista de Datos e Interfaces de Componentes completadas en el SDD con especificaciones técnicas verificables.

---

### M-06 — Mapeo obligatorio de elementos de diseño en la Matriz RTM
* **Situación actual:** No existe trazabilidad entre los requisitos aprobados y los elementos de diseño del sistema (H-06).
* **Situación propuesta:** Todo componente lógico, subsistema e interfaz definidos en el SDD deben estar trazados bidireccionalmente a sus requisitos de origen en la Matriz de Trazabilidad de Requisitos (RTM). El Analista de Gobernanza y Diseño actualiza la columna de diseño de la RTM al completar cada elemento del SDD.
* **Justificación:** CMMI-DEV v2.0 TS SP 2.2 e ISO/IEC 12207 establecen que la trazabilidad bidireccional entre requisitos y elementos de diseño es un control obligatorio para garantizar la completitud del diseño y facilitar el análisis de impacto ante cambios.
* **Artefacto asociado:** N/A (se actualiza la RTM general)
* **Evidencia de cumplimiento:** Columna de diseño de la RTM en [[00-Indice_Procesos.md]] actualizada con el 100% de los requisitos mapeados a elementos del SDD.

---

### M-07 — Inspección formal del SDD mediante checklist de verificación con ciclo de rechazo
* **Situación actual:** No existe ningún mecanismo de control de calidad sobre los artefactos de diseño (H-07).
* **Situación propuesta:** El SDD completado debe ser sometido a una inspección formal por parte del Revisor SQA utilizando el checklist [[CHK-Verificacion_Diseño.md]]. La verificación evalúa la completitud de las vistas arquitectónicas, la consistencia de las interfaces, la trazabilidad con la RTM y la conformidad con IEEE Std 1016.
* **Ciclo de rechazo y reproceso:** Si el revisor califica cualquier ítem obligatorio como `No cumple`, el SDD se rechaza formalmente. El Analista de Gobernanza y Diseño recibe la lista de observaciones y dispone de un plazo máximo de 24 horas para corregir las no conformidades y volver a someter el diseño a verificación.
* **Justificación:** CMMI-DEV v2.0 PPQA SP 1.1 e IEEE 1028-2008 establecen la inspección por pares como la práctica más costo-eficiente de control de defectos en artefactos de ingeniería de software.
* **Artefacto asociado:** [[CHK-Verificacion_Diseño.md]]
* **Evidencia de cumplimiento:** Checklist de verificación completado y firmado digitalmente por el Revisor SQA asociado a cada versión del SDD liberada a codificación.

---

## 5. Limitaciones del Plan
* **Calidad de los Requisitos:** La precisión de la arquitectura está limitada por la completitud y claridad de las fichas de requisitos de la Fase 02. Requisitos ambiguos producirán diseños deficientes.
* **Curva de Aprendizaje:** El equipo de desarrollo puede requerir capacitación inicial sobre el uso formal de herramientas de diagramación Mermaid.js y la notación de IEEE Std 1016.
* **Cambios Dinámicos de Base de Datos:** Cambios estructurales drásticos de persistencia durante fases tardías no pueden resolverse únicamente con el diseño, requiriendo re-evaluaciones completas de impacto en la RTM.
