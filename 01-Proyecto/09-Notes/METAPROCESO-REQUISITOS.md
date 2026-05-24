# Metaproceso de Reingeniería de Procesos (00-PROC-0X) y Causalidad SQA

**Código de Registro:** MET-09-02  
**Responsable de Redacción:** Analista de Gobernanza y Diseño  
**Fecha de Elaboración:** 24 de Mayo de 2026  
**Entradas:** Prácticas empíricas iniciales del equipo (Línea Base), directrices de la minuta de alineación `MIN-09-01` y literatura académica de SQA (Daniel Galin, William E. Lewis, SWEBOK v4, Regan).  
**Salidas:** Estándar supremo del metaproceso para el modelado de procesos `00-PROC-0X`, estructura unificada de 4 componentes para actividades y plan de acción de XookTech v2.0.  
**Propósito:** Redefinir e institucionalizar la metodología del Metaproceso para la creación de los procesos `00-PROC-0X` del SGC, estableciendo el flujo formal donde el diagnóstico empírico y el análisis científico actúan como el detonante directo para estructurar el verdadero proceso de ingeniería ejecutable y su aseguramiento de calidad (SQA).

---

## 1. El Concepto del Metaproceso (Reingeniería de Procesos)

Un proceso del Sistema de Gestión de Calidad (SGC) no debe ser una imposición teórica desconectada de la realidad operativa del equipo. Para que sea legítimo y efectivamente seguible, cada proceso institucional (identificado bajo la nomenclatura `00-PROC-0X`) debe construirse a través de una **reingeniería de procesos estructurada**.

El **Metaproceso** es el estándar metodológico que el equipo de SQA utiliza para analizar las prácticas empíricas iniciales y transformarlas en procesos de ingeniería disciplinados, accionables y auditables.

```
[Práctica Empírica Real]  <-- (Entrada del Metaproceso)
          |
          v
[Análisis Científico SQA] <-- (Filtro Metodológico de Notas Técnicas)
          |
          v
[El Verdadero Proceso]    <-- (Sugerencia Ejecutable y Seguible)
```

---

## 2. La Estructura Unificada de Actividades en los Procesos `00-PROC-0X`

Para asegurar la uniformidad documental y el rigor técnico en toda la bóveda de Obsidian, **cada paso o actividad** de los procesos `00-PROC-0X` se estructurará obligatoriamente bajo los siguientes 4 componentes metodológicos secuenciales:

```
+------------------------------------------------------------+
| 1. DISPARADOR (TRIGGER) Y ARTEFACTO INICIAL                |
|    - Evento o insumo empírico que inicia la actividad.     |
+------------------------------------------------------------+
                              |
                              v
+------------------------------------------------------------+
| 2. ACTUALMENTE (LA PRÁCTICA EMPÍRICA)                      |
|    - Descripción de cómo se ejecuta hoy de forma informal. |
+------------------------------------------------------------+
                              |
                              v
+------------------------------------------------------------+
| 3. NOTA TÉCNICA / JUSTIFICACIONES                          |
|    - Respaldado bibliográfico del porqué requiere control. |
+------------------------------------------------------------+
                              |
                              v
+------------------------------------------------------------+
| 4. LA SUGERENCIA (EL VERDADERO PROCESO)                    |
|    - El paso de ingeniería definitivo, seguible y medible. |
+------------------------------------------------------------+
```

### A. Desglose de los Componentes:
1.  **Disparador (Trigger) y Artefacto Inicial:** Define el evento específico del mundo real o el insumo empírico (ej. un correo del PO, una charla informal, un commit de código) que da inicio a la actividad, identificando el artefacto base o informal de entrada.
2.  **Actualmente (La Práctica Empírica):** Describe detalladamente y de forma honesta cómo se ejecuta la actividad en el estado inicial de la organización, exponiendo sus carencias, falta de control físico y la ausencia de validaciones de calidad.
3.  **Nota Técnica / Justificaciones:** Justificación teórica basada en normas internacionales (ISO, IEEE), modelos de madurez (CMMI) o autores clásicos de SQA (Daniel Galin, William E. Lewis, Regan, SWEBOK v4) que demuestra *por qué* la práctica empírica actual introduce deuda técnica, ambigüedad o inestabilidad.
4.  **La Sugerencia (El Verdadero Proceso):** Representa el **verdadero paso del proceso final**. Es la combinación optimizada de la realidad del equipo ("Actualmente") enriquecida con las herramientas de calidad ("Sugerencias"). Este paso debe ser **completamente seguible, metodológico y claro**, detallando:
    *   Qué rol despersonalizado ejecuta el paso.
    *   Qué acciones secuenciales físicas se realizan en el disco/Obsidian.
    *   Qué artefacto físico formal de salida se produce (con su ID único).
    *   Cómo interviene el control de SQA para verificar la salida.

---

## 3. Aplicación del Metaproceso en la Fase 02: Especificación de Requisitos

Como caso de estudio supremo para el SGC, se detalla la modelación de las actividades del proceso de **Especificación de Requisitos (`00-PROC-02`)** bajo esta nueva concepción metodológica unificada de 4 componentes:

### Actividad 1: Capturar la solicitud de requisito
*   **1. Disparador y Artefacto Inicial:** Mensaje de chat (WhatsApp), correo electrónico informal o notas rápidas de una reunión informal con el Product Owner (PO). El artefacto inicial es la *solicitud empírica e informal del cliente*.
*   **2. Actualmente:** El PO o los programadores sugieren nuevas ideas de palabra o por chats dispersos. Estas solicitudes se pierden, se olvidan o se codifican directamente sin estimar el impacto, provocando un descontrol de alcance (*Scope Creep*).
*   **3. Nota Técnica / Justificaciones:** De acuerdo con CMMI-DEV v1.3 (área de proceso REQM) y **Regan (2002)**, capturar requisitos de forma informal es el detonante del descontrol de alcance y retrasos. Centralizar e identificar de forma única las solicitudes en un archivo físico de entrada previene la pérdida de control técnico.
*   **4. La Sugerencia (El Verdadero Proceso):** 
    *   *Actores:* Analista de Requerimientos.
    *   *Acción:* El analista toma el mensaje informal del PO (disparador) y crea físicamente una nota en la subcarpeta de pendientes de Obsidian: `09-Notes/Simulacion-02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/REQ-XXX.md`.
    *   *Contenido:* Registra el ID estructurado del requerimiento, el link a su solicitud de cambio (`CR-XXX`) y la transcripción textual del mensaje del PO, marcando el estado inicial como "Pendiente".

---

### Actividad 2: Especificar y estructurar el requisito
*   **1. Disparador y Artefacto Inicial:** La existencia de la ficha de requerimiento inicial `REQ-XXX` en estado "Pendiente" en la carpeta de pendientes.
*   **2. Actualmente:** Los requerimientos se detallan con enunciados subjetivos y ambiguos en el cuerpo de la nota (ej. *"el sistema debe cargar las imágenes de forma rápida"*), sin establecer reglas de negocio medibles ni criterios de aceptación.
*   **3. Nota Técnica / Justificaciones:** El **SWEBOK v4** (capítulo de Requisitos) y **William E. Lewis (2009)** enfatizan que un requisito debe ser verificable y libre de ambigüedad. La adopción de escenarios de aceptación estructurados bajo la notación BDD (**Dado/Cuando/Entonces**) y límites numéricos claros provee las precondiciones necesarias para el diseño de pruebas objetivas.
*   **4. La Sugerencia (El Verdadero Proceso):**
    *   *Actores:* Analista de Requerimientos.
    *   *Acción:* El analista edita la nota `REQ-XXX` en pendientes y aplica la plantilla formal de especificación.
    *   *Contenido:* Define de forma obligatoria las reglas de negocio técnicas (ej. formatos, tamaño límite de 10 MB, resolución mínima) y redacta los escenarios de aceptación bajo la estructura BDD (Happy Path, flujos alternativos y flujos de excepción), configurando un insumo de ingeniería completamente seguible por el programador.

---

### Actividad 3: Validar y aprobar el requisito con el Product Owner
*   **1. Disparador y Artefacto Inicial:** Ficha de requerimiento `REQ-XXX` especificada formalmente bajo criterios BDD y lista para revisión.
*   **2. Actualmente:** El equipo asume que la especificación es correcta e inicia la programación a ciegas, sin solicitar aprobación del PO. Al final del ciclo, el entregable es rechazado por el cliente por no alinearse con sus expectativas originales.
*   **3. Nota Técnica / Justificaciones:** **Daniel Galin (2004)** conceptualiza la aprobación del cliente como un contrato de calidad técnico. **Regan (2002)** sostiene que la confirmación explícita y escrita (captura de correo o mensaje del canal oficial) es la única evidencia objetiva que deslinda la responsabilidad de SQA ante discrepancias de alcance.
*   **4. La Sugerencia (El Verdadero Proceso):**
    *   *Actores:* Analista de Requerimientos.
    *   *Acción:* El analista presenta la ficha BDD de `REQ-XXX` al PO para su revisión.
    *   *Contenido:* Resuelven inconsistencias en sesión y, tras la aceptación del PO, el analista inyecta la captura de pantalla o texto íntegro de la confirmación escrita del cliente en la sección de "Evidencia de Aprobación" de la nota, cambiando su estado formal a "Aprobado".

---

### Actividad 4: Línea Base de Requisitos y Trazabilidad SQA
*   **1. Disparador y Artefacto Inicial:** Ficha de requerimiento `REQ-XXX` en estado "Aprobado" y con su evidencia de aprobación inyectada.
*   **2. Actualmente:** Las notas aprobadas y pendientes se mantienen en la misma carpeta desordenada. No se sabe qué está listo para desarrollo, y no hay mapeo hacia los casos de diseño o de prueba del sistema.
*   **3. Nota Técnica / Justificaciones:** CMMI-DEV (área de proceso CM) exige el control de configuración físico (segregación de directorios) para proteger la Línea Base estable. **Lewis (2009)** sustenta que SQA requiere trazabilidad bidireccional desde el requerimiento hasta el código y los casos de prueba para garantizar la cobertura del 100% y facilitar el análisis de impacto.
*   **4. La Sugerencia (El Verdadero Proceso):**
    *   *Actores:* Analista de Requerimientos y Analista de Control y Cambios.
    *   *Acción de Ingeniería:* El Analista de Requerimientos mueve físicamente la nota `REQ-XXX` desde la carpeta de pendientes a la de aprobados oficiales (`01-Ingenieria_Requisitos/01-Aprobados/`) y actualiza la Matriz de Trazabilidad RTM (`01-STD-03_Matriz_Trazabilidad.md`).
    *   *Acción SQA (Control de Calidad):* El Analista de Control y Cambios evalúa de forma independiente el requerimiento utilizando el checklist `CL-02` y firma el dictamen de conformidad en el registro formal `REG-02-01_Verificacion_Requisitos.md`, autorizando su congelamiento y uso como *Entry Criteria* para desarrollo (Fase 04) y diseño de casos de prueba (Fase 05).

---

## 4. Conclusión e Impacto de Madurez en XookTech v2.0

La adopción de este metaproceso refinado de 4 componentes:
1.  **Transparenta el Origen:** Cada actividad formal en Obsidian nace de un disparador del mundo real, eliminando el modelado de procesos abstractos.
2.  **Educa al Equipo:** Explica el "porqué" de cada control de ingeniería a través de justificaciones académicas sólidas.
3.  **Provee Seguibilidad Absoluta:** Asegura que las sugerencias de SQA se fusionen orgánicamente con el trabajo actual, produciendo procesos reales y prácticos que cualquier integrante del equipo puede ejecutar de forma 100% sistemática.
