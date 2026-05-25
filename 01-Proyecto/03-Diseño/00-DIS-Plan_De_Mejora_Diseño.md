# Plan de Mejora — Diseño de Software

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Diagnóstico As-Is del proceso de diseño (inexistente), estándares de arquitectura IEEE Std 1016-2009, directrices CMMI-DEV v2.0 TS y requisitos técnicos del sistema.  
**Salidas:** Proceso de diseño formalizado, Documento de Descripción de Diseño (SDD) bajo IEEE Std 1016, diagramas de arquitectura en Mermaid.js, checklist de verificación de diseño y registros de decisiones técnicas.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Diseño de la Arquitectura y Componentes de Software |
| Documento base | [00-DIS-Documentacion_Diseño.md](00-DIS-Documentacion_Diseño.md) |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 1.0 |
| Fecha | 2026-05-25 |

---

## 2. Objetivo de la Mejora
Implantar desde cero un proceso de diseño de software disciplinado y verificable en XookTech. Se busca establecer la producción obligatoria de un Documento de Descripción de Diseño (SDD) basado en IEEE Std 1016, definir formalmente la arquitectura lógica y física del sistema mediante diagramas técnicos, especificar interfaces y modelos de datos antes de iniciar la codificación, y garantizar la trazabilidad bidireccional entre requisitos aprobados y elementos de diseño.

## Tipo de intervención
☐ Mejora de proceso existente  
☒ Implantación de proceso inexistente

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | No existe una fase de diseño de software formalizada en el ciclo de vida. | **M-01** Implantación del proceso formal de diseño arquitectónico con modelo ETVX. |
| **H-02** | No se produce un Documento de Descripción de Diseño (SDD). | **M-02** Redacción obligatoria del SDD bajo plantilla IEEE Std 1016. |
| **H-03** | Las decisiones tecnológicas no se documentan ni justifican. | **M-03** Registro formal de decisiones de arquitectura y selección de componentes. |
| **H-04** | No existen diagramas de descomposición, comportamiento ni vista física. | **M-04** Producción obligatoria de diagramas arquitectónicos en Mermaid.js. |
| **H-05** | El modelo de datos y las interfaces se definen improvisadamente. | **M-05** Especificación formal del modelo de datos e interfaces de componentes. |
| **H-06** | Ausencia de trazabilidad bidireccional requisitos–diseño. | **M-06** Mapeo obligatorio de elementos de diseño en la Matriz RTM. |
| **H-07** | No existe checklist de verificación de calidad de diseño. | **M-07** Inspección formal del SDD mediante checklist de verificación con ciclo de rechazo. |

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
*   **Situación actual:** XookTech no cuenta con ninguna fase de diseño de software. La transición de requisitos a codificación es directa e informal (H-01).
*   **Situación propuesta:** Se establece como obligatorio un proceso de diseño de software que se ejecute después de la aprobación de requisitos y antes del inicio de la codificación. El proceso se rige por el modelo ETVX: los criterios de entrada exigen requisitos aprobados y firmados; las tareas incluyen la producción del SDD, diagramas y modelo de datos; la salida es el paquete de diseño verificado; y la verificación la realiza el Revisor SQA mediante checklist formal.
*   **Justificación:** ISO/IEC 12207 §6.4.4 establece que todo ciclo de vida de software debe incluir un proceso de diseño arquitectónico que transforme los requisitos en una descripción de diseño verificable antes de la implementación.
*   **Artefacto asociado:** [PLT-FOR_Plantilla_SDD.md](Plantillas/Formatos/PLT-FOR_Plantilla_SDD.md)
*   **Evidencia de cumplimiento:** Existencia del directorio `03-Diseño/` en el SGC con la documentación, el plan de mejora, el checklist y las plantillas completas del proceso.

---

### M-02 — Redacción obligatoria del SDD bajo plantilla IEEE Std 1016
*   **Situación actual:** No se produce ningún documento de diseño que guíe la codificación. Los programadores codifican a partir de instrucciones verbales (H-02).
*   **Situación propuesta:** Es obligatorio producir un Documento de Descripción de Diseño de Software (SDD) utilizando la plantilla formal `PLT-FOR_Plantilla_SDD.md` antes de iniciar cualquier actividad de codificación. El SDD debe incluir las cuatro vistas arquitectónicas de IEEE Std 1016: descomposición, comportamiento lógico, vista física y vista de datos.
*   **Justificación:** IEEE Std 1016-2009 define la estructura mínima de un SDD y establece que la descripción del diseño debe contener múltiples puntos de vista (viewpoints) para garantizar la comprensión completa de la arquitectura.
*   **Artefacto asociado:** [PLT-FOR_Plantilla_SDD.md](Plantillas/Formatos/PLT-FOR_Plantilla_SDD.md)
*   **Evidencia de cumplimiento:** SDD completado y almacenado en el SGC con las cuatro vistas arquitectónicas redactadas y verificadas mediante el checklist de diseño.

---

### M-03 — Registro formal de decisiones de arquitectura y selección de componentes
*   **Situación actual:** Las decisiones tecnológicas (como la selección de frameworks web, librerías de procesamiento de datos o motores de base de datos) se toman de manera implícita y no se registran (H-03).
*   **Situación propuesta:** Toda decisión de arquitectura relevante debe documentarse en el SDD incluyendo: las alternativas evaluadas, los criterios de selección, la justificación técnica de la alternativa elegida y los riesgos identificados.
*   **Justificación:** CMMI-DEV v2.0 TS SP 1.1 (Selección de Soluciones de Componentes de Producto) establece que se deben evaluar y documentar las alternativas de solución técnica con criterios objetivos antes de comprometerse con una implementación.
*   **Artefacto asociado:** [PLT-REG_Decisiones_Arquitectura.md](Plantillas/Registros/PLT-REG_Decisiones_Arquitectura.md)
*   **Evidencia de cumplimiento:** Registro de Decisiones de Arquitectura completado con al menos una entrada por cada tecnología crítica del sistema.

---

### M-04 — Producción obligatoria de diagramas arquitectónicos en Mermaid.js
*   **Situación actual:** No existen diagramas de componentes, flujos de sistema ni vistas físicas del software (H-04).
*   **Situación propuesta:** El Analista de Gobernanza y Diseño debe producir como mínimo tres diagramas técnicos en formato Mermaid.js antes de liberar el paquete de diseño: (1) diagrama de descomposición lógica de componentes, (2) diagrama de secuencia del comportamiento dinámico y (3) diagrama de la estructura física del repositorio. Estos diagramas se integran al SDD y se producen utilizando la plantilla formal `PLT-FOR_Diagrama_Arquitectura.md`.
*   **Justificación:** IEEE Std 1016-2009 establece que la descripción del diseño debe incluir múltiples puntos de vista (viewpoints) modelados mediante notaciones formales para garantizar la comprensión del sistema por todos los interesados.
*   **Artefacto asociado:** [PLT-FOR_Diagrama_Arquitectura.md](Plantillas/Formatos/PLT-FOR_Diagrama_Arquitectura.md)
*   **Evidencia de cumplimiento:** Diagramas técnicos en Mermaid.js renderizados e incorporados al SDD y verificados en el checklist de diseño.

---

### M-05 — Especificación formal del modelo de datos e interfaces de componentes
*   **Situación actual:** Las tablas de base de datos, esquemas JSON y firmas de funciones se definen ad-hoc durante la codificación (H-05).
*   **Situación propuesta:** Antes de iniciar la codificación, el SDD debe contener: (1) el modelo de datos completo con tipos, llaves primarias, relaciones y restricciones, y (2) la especificación de interfaces de software con las signaturas de funciones críticas, parámetros de entrada/salida, tipos de retorno y códigos de respuesta HTTP.
*   **Justificación:** ISO/IEC 12207 §6.4.4 y SWEBOK v4 Cap. 2 (Diseño de Software) establecen que la especificación de interfaces y modelos de datos es un entregable obligatorio del proceso de diseño que previene acoplamientos fuertes e inconsistencias de persistencia.
*   **Artefacto asociado:** N/A (integrado directamente en las vistas de datos e interfaces del SDD)
*   **Evidencia de cumplimiento:** Secciones de Vista de Datos e Interfaces de Componentes completadas en el SDD con especificaciones técnicas verificables.

---

### M-06 — Mapeo obligatorio de elementos de diseño en la Matriz RTM
*   **Situación actual:** No existe trazabilidad entre los requisitos aprobados y los elementos de diseño del sistema (H-06).
*   **Situación propuesta:** Todo componente lógico, subsistema e interfaz definidos en el SDD deben estar trazados bidireccionalmente a sus requisitos de origen en la Matriz de Trazabilidad de Requisitos (RTM). El Analista de Gobernanza y Diseño actualiza la columna de diseño de la RTM al completar cada elemento del SDD.
*   **Justificación:** CMMI-DEV v2.0 TS SP 2.2 e ISO/IEC 12207 establecen que la trazabilidad bidireccional entre requisitos y elementos de diseño es un control obligatorio para garantizar la completitud del diseño y facilitar el análisis de impacto ante cambios.
*   **Artefacto asociado:** N/A (se actualiza la RTM de la Fase 02)
*   **Evidencia de cumplimiento:** Columna de diseño de la RTM actualizada con el 100% de los requisitos mapeados a elementos del SDD.

---

### M-07 — Inspección formal del SDD mediante checklist de verificación con ciclo de rechazo
*   **Situación actual:** No existe ningún mecanismo de control de calidad sobre los artefactos de diseño (H-07).
*   **Situación propuesta:** El SDD completado debe ser sometido a una inspección formal por parte del Revisor SQA utilizando el checklist `CHK-Verificacion_Diseño.md`. La verificación evalúa la completitud de las vistas arquitectónicas, la consistencia de las interfaces, la trazabilidad con la RTM y la conformidad con IEEE Std 1016.
*   **Ciclo de rechazo y reproceso:** Si el revisor califica cualquier ítem obligatorio como `No cumple`, el SDD se rechaza formalmente. El Analista de Gobernanza y Diseño recibe la lista de observaciones y dispone de un plazo máximo de 24 horas para corregir las no conformidades y volver a someter el diseño a verificación.
*   **Justificación:** CMMI-DEV v2.0 PPQA SP 1.1 e IEEE 1028-2008 establecen la inspección por pares como la práctica más costo-eficiente de control de defectos en artefactos de ingeniería de software.
*   **Artefacto asociado:** [CHK-Verificacion_Diseño.md](Checklists/CHK-Verificacion_Diseño.md)
*   **Evidencia de cumplimiento:** Checklist de verificación completado y firmado digitalmente por el Revisor SQA asociado a cada versión del SDD liberada a codificación.

---

## 5. Proceso To-Be (PROC-03) — Modelo de Especificación ETVX

Este proceso técnico rige el diseño arquitectónico del software bajo el ciclo de mejora continua PDCA y el modelo ETVX:

*   **Disparador:** Aprobación formal de la línea base de requisitos en la Fase 02 o recepción de una Solicitud de Cambio (`CR-XXX`) que impacte la arquitectura.
*   **Criterio de Entrada (Entry Criteria):** Contar con la Especificación de Requisitos de Software (SRS) aprobada y la Matriz de Trazabilidad de Requisitos (RTM) actualizada.

### Matriz de Tareas — Entradas, Actividades y Salidas

| Entrada (Input) | Actividad (Task) | Salida (Output) |
| :--- | :--- | :--- |
| `SRS Aprobada` / `CR` | **Paso 1 — Análisis de viabilidad arquitectónica:** Revisión de los requisitos aprobados para identificar restricciones tecnológicas, patrones de diseño aplicables y alternativas de solución. | `Registro de Decisiones de Arquitectura` |
| `Registro de Decisiones` | **Paso 2 — Selección de componentes y tecnologías:** Evaluación formal de alternativas tecnológicas (frameworks, motores de base de datos, librerías de procesamiento) y registro de la justificación de selección con criterios objetivos. | `Sección SP 1.1 del SDD completada` |
| `Requisitos + Decisiones` | **Paso 3 — Modelado de descomposición lógica:** Producción del diagrama de componentes del sistema utilizando la plantilla de diagramas Mermaid.js, identificando subsistemas, capas y responsabilidades. | `Diagrama de Descomposición (Vista Lógica)` |
| `Diagrama de Descomposición` | **Paso 4 — Modelado de comportamiento dinámico:** Producción del diagrama de secuencia que describe la interacción temporal entre componentes, el flujo de datos y los escenarios de error. | `Diagrama de Secuencia (Vista de Comportamiento)` |
| `Requisitos de Persistencia` | **Paso 5 — Diseño del modelo de datos:** Definición del esquema de persistencia (tablas, llaves, tipos, restricciones) y las estructuras de datos internas del sistema. | `Modelo de Datos (Vista de Datos)` |
| `Diagramas + Modelo de Datos` | **Paso 6 — Especificación de interfaces:** Definición de las signaturas de funciones, rutas de API, parámetros, tipos de retorno y códigos de respuesta HTTP de cada componente. | `Contrato de Interfaces de Software` |
| `Todos los diagramas + Interfaces` | **Paso 7 — Consolidación del SDD:** Integración de todas las vistas arquitectónicas en el Documento de Descripción de Diseño utilizando la plantilla `PLT-FOR_Plantilla_SDD.md`. | `SDD v1.0 Consolidado` |
| `SDD v1.0` | **Paso 8 — Actualización de la RTM:** Mapeo bidireccional de cada elemento de diseño (componente, interfaz, tabla) a su requisito de origen en la Matriz de Trazabilidad. | `RTM Actualizada (columna Diseño)` |
| `SDD + RTM` | **Paso 9 — Verificación formal SQA:** El Revisor SQA ejecuta el checklist `CHK-Verificacion_Diseño.md` sobre el SDD y dictamina la conformidad. | `Checklist Firmado` / `Lista de No Conformidades` |
| `Checklist Aprobado` | **Paso 10 — Liberación del paquete de diseño:** El SDD verificado y los diagramas se incorporan a la línea base del SGC como criterio de entrada obligatorio para la Fase 04 (Codificación). | `Paquete de Diseño Liberado` |

*   **Criterio de Salida (Exit Criteria):** SDD verificado y aprobado por el Revisor SQA con 0 no conformidades pendientes, RTM actualizada con el 100% de cobertura, y paquete de diseño incorporado a la línea base del SGC.
*   **Criterio de Verificación:** Checklist `CHK-Verificacion_Diseño.md` completado y firmado digitalmente. Cobertura de requisitos en el diseño = 100%.

---

## 6. Indicadores de Éxito
| Indicador                         | Métrica                                                             | Meta     | Justificación de la Meta                                              |
| --------------------------------- | ------------------------------------------------------------------- | -------- | --------------------------------------------------------------------- |
| Cobertura de requisitos en diseño | % de requisitos aprobados mapeados a elementos del SDD.             | `100%`   | Puerta de control obligatoria para garantizar completitud del diseño. |
| Completitud del SDD               | % de vistas arquitectónicas (4/4) completadas en el documento.      | `100%`   | IEEE Std 1016 exige las cuatro vistas mínimas.                        |
| Densidad de defectos de diseño    | Defectos detectados en inspección / Total de componentes diseñados. | `≤ 0.10` | Meta de calidad para minimizar retrabajo en codificación.             |
| Control de calidad previo         | % de SDDs liberados con checklist de verificación aprobado.         | `100%`   | Puerta de control obligatoria antes de la transición a codificación.  |


---

## 7. Limitaciones del Plan
*   **Dependencia de la Fase 02:** La calidad del diseño está directamente limitada por la calidad y completitud de los requisitos aprobados. Requisitos incompletos o ambiguos producirán diseños deficientes.
*   **Curva de aprendizaje:** El equipo de XookTech no tiene experiencia previa en la producción formal de artefactos de diseño bajo IEEE Std 1016, lo que puede ralentizar las primeras iteraciones del proceso.
*   **Alcance del modelo de datos:** El diseño del modelo de datos se limita a las estructuras de persistencia requeridas por los requisitos actuales y no anticipa extensiones futuras no contempladas en la SRS.
