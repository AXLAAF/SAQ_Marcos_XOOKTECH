# Plan de Mejora de Requisitos (To-Be)

**Responsable:** Analista de Requerimientos  
**Entradas:** Documentación del proceso de requisitos (As-Is), análisis de brechas de calidad SQA y directrices organizacionales para CMMI Nivel 2.  
**Salidas:** Modelo del proceso to-be, matriz de implementación de prácticas CMMI-DEV v2.0, métricas de calidad y criterios de verificación SQA.  

---

## 1. Introducción y Nivel de Madurez

El presente plan establece el modelo de proceso optimizado (To-Be) para la Fase de Requisitos del proyecto *Visualizador de Marcos*. El diagnóstico organizacional sitúa a la empresa en un **Nivel 1 (Inicial)** de madurez de procesos de software: las especificaciones son inestables, no hay trazabilidad y la calidad depende de cada persona involucrada en el proyecto. 

El objetivo es escalar al **Nivel 2 (Gestionado)** de **CMMI-DEV v2.0**, garantizando que los requisitos se capturen de manera controlada, se validen formalmente y mantengan una trazabilidad a lo largo del ciclo de vida del software.

---

## 2. Área de Proceso Aplicable: Requirements Management (REQM)

Para satisfacer las demandas de CMMI Nivel 2, se adopta el área de proceso **Requirements Management (REQM)**. Su objetivo es asegurar que los requisitos del sistema se gestionen adecuadamente y que se identifiquen y resuelvan las inconsistencias entre los requisitos, los planes del proyecto y los entregables de ingeniería.

---

## 3. Prácticas Específicas CMMI (SP 1.1 a SP 1.5) e Implementación

El proceso To-Be se estructurará mediante la implementación de las siguientes 5 prácticas específicas:

### SP 1.1: Obtener un Entendimiento de los Requisitos
*   **Implementación:** Se define el uso mandatorio de la plantilla oficial de Especificación de Requisitos de Software (`PLT-SRS.md`) basada en la norma **IEEE Std 830** y el modelado de escenarios de aceptación estructurados en formato BDD (`Dado / Cuando / Entonces`) para cada funcionalidad técnica.
*   **Justificación Técnica (NT-01):** Según **Daniel Galin 2004** y **SWEBOK v4.0**, un entendimiento unificado entre el cliente y el equipo técnico requiere criterios de aceptación objetivos y medibles. El lenguaje BDD elimina la ambigüedad semántica intrínseca del lenguaje natural libre, permitiendo a los programadores y verificadores trabajar sobre la misma base lógica.

### SP 1.2: Obtener Compromiso con los Requisitos
*   **Implementación:** Todo requerimiento redactado por el Analista de Requisitos debe someterse a una revisión con el Product Owner. La aprobación digital se inyecta en el documento solo tras alcanzar un acuerdo mutuo.
*   **Justificación Técnica (NT-02):** **Regan 2002** postula que el compromiso formal previene la desviación del alcance y establece una frontera contractual clara de responsabilidad. La aprobación digital actúa como el *Exit Criteria* definitivo de la especificación técnica.

### SP 1.3: Gestionar los Cambios a los Requisitos
*   **Implementación:** Se prohíbe cualquier edición directa sobre archivos en la carpeta de aprobados. Todo cambio o nuevo requerimiento debe pasar mediante una Solicitud de Cambio formal (`TEMPLATE-CR.md`) ante el Analista de Control y Cambios bajo el proceso `PROC-05.1_Control_Cambios`.
*   **Justificación Técnica (NT-03):** De acuerdo con **William E. Lewis 2009**, la inestabilidad de requisitos sin control de cambios (*requirements creep*) destruye la planificación del proyecto. La gestión formal de cambios resguarda la integridad de la Línea Base.

### SP 1.4: Mantener Trazabilidad Bidireccional de los Requisitos
*   **Implementación:** Se implementa de forma mandatoria la Matriz de Trazabilidad RTM [[01-STD-03_Matriz_Trazabilidad.md]]. Cada ID de requisito (`REQ-XX`) debe estar mapeado a su documento de diseño de sistema (`STD-XX`), código fuente en Git y caso de prueba (`CP-XX`).
*   **Justificación Técnica (NT-04):** **SWEBOK v4.0** destaca que la trazabilidad bidireccional es indispensable para realizar análisis de impacto confiables y garantizar que todo requerimiento aprobado sea efectivamente codificado y verificado sin dejar brechas.

### SP 1.5: Identificar Inconsistencias entre el Trabajo del Proyecto y los Requisitos
*   **Implementación:** El Analista de Control y Cambios realizará auditorías documentales periódicas sobre los entregables de diseño, código y pruebas. Cualquier discrepancia detectada se registrará como una no conformidad formal en el Dashboard de Calidad (`STD-08`).
*   **Justificación Técnica (NT-05):** **Daniel Galin 2004** conceptualiza el aseguramiento de calidad (SQA) como el supervisor de la fidelidad del producto final respecto al contrato original. Esta práctica garantiza la alineación del ciclo de vida del software con las expectativas iniciales.

## 4. Criterios de Éxito y Verificación

El éxito del plan de mejora se constatará en las auditorías de calidad mediante el cumplimiento del 100% de los siguientes criterios objetivos:

*   **Conformidad de documentos:** El 100% de las fichas de requisitos de la bóveda cumplen con la plantilla oficial.
*   **Sincronización RTM:** La Matriz de Trazabilidad RTM no presenta celdas marcadas como "TBD" para ningún requerimiento que forme parte de la línea base aprobada.
*   **Validación de Cambios:** El 100% de las modificaciones al conjunto de requirimientos cuentan con un formato de Solicitud de Cambio formal aprobado e incorporado en la carpeta de revisiones.

---

## 5. Control de Entregables Generados

A continuación se detalla la gobernanza del presente documento de mejora:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Plan de Mejora de Requisitos (To-Be) | REQ-PLM-01 | CMMI-DEV v2.0 - REQM | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
