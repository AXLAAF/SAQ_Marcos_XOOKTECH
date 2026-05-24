# Plan de Metaproceso y Causalidad SQA — Fase de Requisitos

**Código de Registro:** MET-02-01  
**Responsable de Redacción:** Analista de Gobernanza y Diseño  
**Fecha de Elaboración:** 24 de Mayo de 2026  
**Entradas:** Prácticas empíricas iniciales (Línea Base), minutas de alineación `MIN-09-01`, solicitudes originales del Product Owner y normas SQA (CMMI-DEV, Daniel Galin, Regan, SWEBOK v4, Lewis).  
**Salidas:** Modelo del metaproceso de requisitos, estructura unificada de 4 componentes para `00-PROC-02`, simulación del ciclo de vida de `REQ-01` y auditoría correctiva SQA de `REQ-07`.  
**Propósito:** Detallar, justificar y simular de forma integral el metaproceso de reingeniería aplicada sobre la Fase 02 - Requisitos, evidenciando científicamente cómo la triada Actualmente/Nota/Propuesta detona la transición formal de solicitudes vagas a artefactos BDD estables bajo control de configuración SQA.

---

## 1. El Metaproceso de Requisitos: Justificación y Causalidad SQA

El **Metaproceso de Requisitos** es el estándar de reingeniería que rige el diseño de la Fase 02 del SGC. Su propósito es transparentar cómo las necesidades empíricas del proyecto *Visualizador de Marcos* son capturadas, analizadas a través de la literatura académica e integradas en un proceso de ingeniería de software disciplinado, seguible y verificable por el Aseguramiento de Calidad (SQA).

```
[Disparador e Insumo Vago] ---> [Metaproceso SQA] ---> [Proceso de Ingeniería (00-PROC-02)]
                                                           |
                                                           +--> Fichas REQ BDD estables
                                                           +--> Matriz RTM sincronizada
                                                           +--> Checklist y Registro SQA
```

Para asegurar que cada paso del proceso sea completamente ejecutable y metodológico, las actividades de la **Especificación de Requisitos (`00-PROC-02`)** se modelan bajo la estructura unificada de **4 componentes**:

### Actividad 1: Capturar la solicitud de requisito
1.  **Disparador y Artefacto Inicial:** Conversación verbal, correo no estructurado o mensaje informal de mensajería (WhatsApp) por parte del Product Owner (PO). El artefacto inicial es la *solicitud empírica de funcionalidad*.
2.  **Actualmente:** Las nuevas ideas y funciones se sugieren informalmente. Al no existir un control de entradas físicas, las solicitudes se pierden, se olvidan o se programan a ciegas, provocando un descontrol del alcance (*Scope Creep*) y estimaciones de tiempo obsoletas.
3.  **Nota Técnica / Justificaciones:** De acuerdo con CMMI-DEV v1.3 (área de proceso REQM) y **Regan (2002)**, la captura informal de requisitos es la principal causa de desvíos en el alcance. Centralizar e identificar de forma única cada petición en una nota física de entrada previene la pérdida de control y formaliza la entrada técnica.
4.  **La Sugerencia (El Verdadero Proceso):** El *Analista de Requerimientos* toma el disparador e inicializa una ficha individual en la carpeta de pendientes: `09-Notes/Preview-02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/REQ-XXX.md`, asignándole un ID estructurado, su Change Request de origen y la descripción de la petición, en estado "Pendiente".

---

### Actividad 2: Especificar y estructurar el requisito
1.  **Disparador y Artefacto Inicial:** Ficha del requerimiento `REQ-XXX` registrada en estado "Pendiente" en la carpeta de pendientes.
2.  **Actualmente:** Los requerimientos se describen en lenguaje natural vago y subjetivo (ej. *"que cargue rápido"*), imposibilitando que los programadores implementen la lógica exacta o que el equipo de pruebas verifique objetivamente la funcionalidad.
3.  **Nota Técnica / Justificaciones:** El **SWEBOK v4** (capítulo de Requisitos) y **William E. Lewis (2009)** exigen que los requisitos sean verificables, medibles y libres de ambigüedad. La adopción de escenarios de aceptación estructurados en formato **BDD (Dado/Cuando/Entonces)** y cotas numéricas claras provee las bases necesarias para el diseño de casos de prueba.
4.  **La Sugerencia (El Verdadero Proceso):** El *Analista de Requerimientos* edita la ficha `REQ-XXX` y aplica la plantilla formal de especificación, detallando las reglas de negocio técnicas (formatos, tamaño límite, rendimiento) y estructurando escenarios BDD legibles y medibles para la Fase 04 (Desarrollo) y Fase 05 (Pruebas).

---

### Actividad 3: Validar y aprobar el requisito con el Product Owner
1.  **Disparador y Artefacto Inicial:** Ficha de requerimiento `REQ-XXX` especificada formalmente en BDD y lista para revisión.
2.  **Actualmente:** Se asume que la especificación técnica de la ficha es lo que el cliente desea. Se inicia la programación sin su validación y, al final, el cliente rechaza el entregable porque "no era lo que tenía en mente".
3.  **Nota Técnica / Justificaciones:** **Daniel Galin (2004)** conceptualiza la aprobación del cliente como un contrato técnico. **Regan (2002)** sustenta que la confirmación escrita explícita (captura de correo o mensajería en la sección "Evidencia de Aprobación") es la única evidencia objetiva que deslinda la responsabilidad de SQA ante discrepancias de alcance.
4.  **La Sugerencia (El Verdadero Proceso):** El *Analista de Requerimientos* presenta la ficha BDD de `REQ-XXX` al PO. Resuelven dudas y, tras la aprobación, el analista inyecta la captura de pantalla de la confirmación escrita en la sección de "Evidencia de Aprobación" del archivo, cambiando su estado formal a "Aprobado".

---

### Actividad 4: Línea Base de Requisitos y Trazabilidad SQA
1.  **Disparador y Artefacto Inicial:** Ficha de requerimiento `REQ-XXX` en estado "Aprobado" y con su evidencia de aprobación inyectada.
2.  **Actualmente:** Los requisitos aprobados y pendientes se mantienen en la misma carpeta. No se sabe qué está listo para desarrollo, y no hay mapeo hacia los casos de diseño o de prueba del sistema.
3.  **Nota Técnica / Justificaciones:** CMMI-DEV (Gestión de Configuración - CM) exige el control de configuración físico (segregación de directorios) para proteger la Línea Base estable. **Lewis (2009)** sustenta que SQA requiere trazabilidad bidireccional desde el requerimiento hasta el código y los casos de prueba para garantizar la cobertura del 100% y facilitar el análisis de impacto.
4.  **La Sugerencia (El Verdadero Proceso):** El *Analista de Requerimientos* mueve físicamente la nota `REQ-XXX` desde la carpeta de pendientes a la de aprobados oficiales (`01-Ingenieria_Requisitos/01-Aprobados/`) y actualiza la Matriz RTM (`01-STD-03_Matriz_Trazabilidad.md`). El *Analista de Control y Cambios* evalúa independientemente el requerimiento con el checklist `CL-02` y firma el dictamen en el registro formal `REG-02-01_Verificacion_Requisitos.md`, autorizando su congelamiento en la Línea Base.

---

## 2. Simulación en Vivo 1: Ciclo de Vida Completo de REQ-01

Para evidenciar la reingeniería en acción, simulamos la ejecución completa del Metaproceso sobre el requerimiento crítico **REQ-01: Carga de Imagen del Cliente**:

### Paso 1: Entrada Empírica (Disparador)
*   **Mensaje de WhatsApp del PO:** *"Necesitamos que el cliente pueda subir una foto de su celular desde la página, que cargue rápido y que no acepte formatos raros, solo fotos comunes. Debe verse bien."*

### Paso 2: Análisis de Calidad SQA (Nota Técnica)
*   El analista identifica ambigüedad en *"que cargue rápido"* (no medible) y *"fotos comunes"* (sin especificación de formato MIME), además de la ausencia de límites de tamaño (riesgo de denegación de servicio en Flask/OpenCV).

### Paso 3: Especificación BDD y Reglas de Negocio (Sugerencia de Ingeniería)
El Analista aplica la plantilla y genera el requerimiento formal BDD en la simulación:
*   **RN-01-01:** Formatos admitidos: Exclusivamente JPEG y PNG.
*   **RN-01-02:** Peso máximo: Límite estricto de 10 MB.
*   **Escenario BDD (Happy Path):**
    *   **Dado** que el cliente se encuentra en la pantalla del visualizador de marcos,
    *   **Cuando** selecciona y sube un archivo de imagen en formato `JPEG` con un tamaño de `4.2 MB`,
    *   **Entonces** el sistema debe validar el formato y tamaño en el servidor Flask,
    *   **Y** renderizar con éxito la imagen en el canvas interactivo en un tiempo inferior a `1.5 segundos`.
*   **Escenarios de Excepción:** Se definieron y estructuraron escenarios BDD explícitos para el bloqueo de formatos no permitidos (ej. PDF) y rechazo por exceso de peso (HTTP 413).

### Paso 4: Auditoría y Aprobación SQA (Línea Base)
*   El Analista de Control y Cambios aplica el checklist `CL-02`. Al constatar el cumplimiento de todos los atributos, firma y emite el dictamen formal en el registro `REG-02-01-REQ-01`, autorizando el traslado del archivo a `01-Aprobados/01-REQ-01_Carga_Imagen.md` e integrándolo a la Matriz RTM.

---

## 3. Simulación en Vivo 2: Control de Cambios y Remediación SQA de REQ-07

Esta simulación recrea cómo el Metaproceso resuelve y controla las solicitudes de cambio a la Línea Base estable, utilizando el caso de **REQ-07: Marcos Dobles** (derivado de `CR-01`):

### Paso 1: Detección de No Conformidad en la Especificación
*   Al evaluar la ficha de pendientes `REQ-07` de la simulación, el Analista de Control y Cambios identificó una no conformidad en la regla de negocio `RN-07-04`, la cual declaraba de forma imprecisa que la *"distancia entre los dos espacios es configurable"*, omitiendo una cota que impidiera el desbordamiento visual del canvas interactivo de marcos en el navegador.

### Paso 2: Acción Correctiva y Remediación de Ingeniería
*   Siguiendo el flujo del Metaproceso, se obligó al *Analista de Requerimientos* a corregir la regla en `REQ-07` fijando la cota física límite en las reglas de negocio:
    *   *RN-07-04 (Corregida):* *"La distancia entre los dos espacios es configurable, con un valor límite máximo de 50 mm para resguardar la paridad del canvas interactivo."*

### Paso 3: Control de Configuración y Aprobación SQA
*   **Aprobación de SQA:** Se modificó el registro formal `REG-02-01` en la simulación, incorporando la auditoría conforme de `REQ-07` y documentando la remediación como una acción correctiva de calidad exitosa.
*   **Firma del Change Request:** El `CR-01` relacionado en la sección de trazabilidad del requerimiento se marcó como **"Aprobado y Firmado"** tras superar las pruebas conceptuales.
*   **Traslado Físico:** Se movió físicamente la nota `07-REQ-07_Marcos_Dobles.md` de la carpeta `00-Pendientes/` a la de `01-Aprobados/`:  
    `09-Notes/Preview-02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/07-REQ-07_Marcos_Dobles.md`
*   **Actualización de Trazabilidad RTM:** Se modificó la Matriz RTM de la simulación (`01-STD-03_Matriz_Trazabilidad.md`), cambiando el estado formal de `REQ-07` de **"Pendiente"** a **"Aprobado"** y enlazándolo bidireccionalmente con el diseño de componentes (`STD-04`) y su caso de prueba (`CP-09`).

---

## 4. Conclusiones del Metaproceso de Requisitos

La ejecución práctica del metaproceso en este Preview de Requisitos demuestra que:
1.  **Cada control tiene causalidad:** El proceso de ingeniería y calidad no es una imposición abstracta; cada plantilla y regla nace de un diagnóstico empírico ("Actualmente") y de una justificación científica ("Nota Técnica").
2.  **Elimina la Deuda Técnica:** Al obligar a especificar bajo escenarios BDD y límites numéricos, se garantiza que los programadores y testers tengan insumos de entrada libres de ambigüedad, previniendo defectos antes de iniciar el código.
3.  **Garantiza el Control del SGC:** A través del control de configuración físico (segregación en `Aprobados` y `Pendientes`) y las auditorías independientes de SQA, se asegura un desarrollo robusto y certificado al 100.00%.
