# Metaproceso de Modelado y Reingeniería de Procesos (00-PROC-0X)

**Código de Registro:** MET-01-01  
**Responsable de Redacción:** Analista de Gobernanza y Diseño  
**Fecha de Elaboración:** 24 de Mayo de 2026  
**Entradas:** Directrices y políticas de calidad institucionales, estándares internacionales de ingeniería de procesos de software (CMMI-DEV v1.3 OPD/OPF, ISO/IEC 12207, SWEBOK v4).  
**Salidas:** Estándar máster global del Metaproceso de modelado de procesos, reglas unificadas de 4 componentes para actividades `00-PROC-0X` e inyección de controles SQA.  
**Propósito:** Definir e institucionalizar la metodología de reingeniería del Metaproceso Global para la creación de los procesos técnicos `00-PROC-0X` en el SGC de XookTech, garantizando que toda actividad responda a una justificación científica y a un flujo de control de calidad objetivo.

---

## 1. El Metaproceso Global: Filosofía de Calidad

En el **Sistema de Gestión de Calidad (SGC)** de XookTech, los procesos no se imponen de forma arbitraria o desconectada de la realidad operativa del equipo. Para garantizar que los procesos sean realistas, ejecutables y útiles, cada proceso técnico (identificado bajo la nomenclatura `00-PROC-0X`) se diseña a través de una **reingeniería de procesos estructurada**.

El **Metaproceso** es el estándar supremo de gobernanza global que reglamenta cómo se modelan las actividades en la organización. Define el ciclo de vida por el cual una práctica empírica informal se somete al análisis científico y metodológico, dando origen al verdadero proceso de ingeniería y a su aseguramiento de calidad (SQA).

```
[Insumo o Práctica Empírica] ---> [Metaproceso Máster] ---> [El Verdadero Proceso (Seguible)]
                                                                   |
                                                                   +--> Fichas y Artefactos Físicos
                                                                   +--> Matriz RTM Bidireccional
                                                                   +--> Control e Inspección SQA
```

---

## 2. El Estándar Unificado de Actividades (El Modelo de 4 Componentes)

Toda actividad o paso que componga un proceso institucional `00-PROC-0X` debe modelarse obligatoriamente bajo la estructura de los siguientes **4 componentes metodológicos secuenciales**:

```
+------------------------------------------------------------+
| 1. DISPARADOR (TRIGGER) Y ARTEFACTO INICIAL                |
|    - El evento real o el insumo empírico que inicia el paso|
+------------------------------------------------------------+
                              |
                              v
+------------------------------------------------------------+
| 2. ACTUALMENTE (LA PRÁCTICA EMPÍRICA)                      |
|    - Cómo se ejecuta hoy en la organización sin controles. |
+------------------------------------------------------------+
                              |
                              v
+------------------------------------------------------------+
| 3. NOTA TÉCNICA / JUSTIFICACIONES                          |
|    - Fundamentación científica (normas/autores de la materia)|
+------------------------------------------------------------+
                              |
                              v
+------------------------------------------------------------+
| 4. LA SUGERENCIA (EL VERDADERO PROCESO)                    |
|    - El paso definitivo, seguible, metodológico y medible. |
+------------------------------------------------------------+
```

### A. Desglose de los Componentes:

1.  **Disparador (Trigger) y Artefacto Inicial:**
    *   *Propósito:* Identificar el evento específico o el insumo empírico de entrada (ej. un correo, una solicitud informal, una alerta del sistema) que detona la actividad en el mundo real.
    *   *Regla:* El proceso debe declarar de manera explícita cuál es el artefacto de entrada (incluso si es informal o de palabra) para evitar el inicio de actividades a ciegas.
2.  **Actualmente (La Práctica Empírica):**
    *   *Propósito:* Documentar con total honestidad cómo ejecuta hoy en día la organización la actividad, identificando las carencias operativas, la falta de control físico y la propensión a la acumulación de deuda técnica o desvíos de alcance.
3.  **Nota Técnica / Justificaciones:**
    *   *Propósito:* Proveer el sustento científico de por qué la práctica informal actual es deficiente o peligrosa.
    *   *Regla:* Debe citar obligatoriamente una norma internacional (ISO, IEEE), un modelo de madurez (CMMI) o un autor clásico de aseguramiento de calidad (Daniel Galin, William E. Lewis, Regan, SWEBOK v4) para dar una justificación rigurosa a la reingeniería.
4.  **La Sugerencia (El Verdadero Proceso):**
    *   *Propósito:* Definir el paso de ingeniería definitivo que se convierte en el **verdadero proceso ejecutable y seguible**.
    *   *Regla:* Combina la realidad operativa de la organización con la disciplina de la ingeniería. Debe ser completamente claro, paso a paso, y detallar:
        *   Qué **rol despersonalizado** ejecuta la acción.
        *   Qué tareas secuenciales físicas se realizan en Obsidian o en el disco.
        *   Qué **artefacto físico formal de salida** se produce (con su ID estructurado).
        *   Qué **control de SQA** valida la salida antes de permitir el avance de fase.

---

## 3. Arquitectura del SGC: Segregación Física de Conceptos

Para que el SGC sea legible y mantenga un alto rigor metodológico, la estructura de carpetas en cada fase técnica del proyecto debe segregarse de forma obligatoria en dos grandes subcarpetas bajo el principio de independencia de SQA:

*   **Subcarpeta `01-Ingenieria_[Fase]` (La Construcción):**  
    Alberga de forma estricta los procesos ejecutables (`00-PROC-0X`), los entregables de diseño, el inventario de código y las fichas de especificación funcional en formato BDD. Describe cómo los ingenieros construyen el software.
*   **Subcarpeta `02-Calidad_[Fase]` (La Verificación):**  
    Alberga de forma estricta los checklists de calidad (`CL`), las actas de inspección (`INS`), los informes de hallazgos y los registros formales de aprobación de SQA (`REG`). Describe cómo el equipo independiente de calidad verifica que lo construido cumpla con el estándar.

---

## 4. Inyección del Ciclo de Mejora Continua PDCA (Ciclo Deming)

Cada proceso `00-PROC-0X` debe inyectar el ciclo de mejora continua **PDCA** (Planear, Hacer, Verificar, Actuar) para asegurar la retroalimentación y evolución del sistema de calidad:

```
[PLANEAR]  --> Definición y estimación en pendientes (Ingeniería)
    |
    v
[HACER]    --> Especificación y construcción del artefacto (Ingeniería)
    |
    v
[VERIFICAR]--> Auditoría y checklist independiente SQA (Calidad SQA)
    |
    v
[ACTUAR]   --> Registro de defectos, remediación y Línea Base (Calidad SQA)
```

1.  **Planear (Plan):** El Analista de Requerimientos y Diseño planifica el alcance y registra los artefactos en estado pendiente (`00-Pendientes/`).
2.  **Hacer (Do):** El equipo de ingeniería construye y detalla el artefacto siguiendo las reglas de negocio técnicas y el formato BDD.
3.  **Verificar (Check):** El Analista de Control y Cambios evalúa el artefacto con el checklist independiente de calidad, detectando y reportando no conformidades.
4.  **Actar (Act):** Se resuelven las no conformidades (remediación), se documenta el dictamen conforme en el registro de calidad y se traslada formalmente el archivo a la Línea Base estable (`01-Aprobados/`), retroalimentando el proceso para evitar futuras fallas.

---

## 5. Referencias Máster de Gobernanza

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Ingeniería de Procesos de Software.  
[2] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Modelado e Infraestructura Contractual).  
[3] CMMI-DEV v1.3. _CMMI para Desarrollo_, Software Engineering Institute. Áreas de proceso: Enfoque en Procesos de la Organización (OPF) y Definición de Procesos de la Organización (OPD).  
[4] ISO/IEC 12207:2017. _Sistemas e Ingeniería de Software — Procesos del Ciclo de Vida del Software_.  
