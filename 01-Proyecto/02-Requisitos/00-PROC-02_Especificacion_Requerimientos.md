# Proceso de Especificación de Requisitos — XookTech
**Responsable:** Analista de Requerimientos
**Entradas:** Línea Base y Especificaciones Iniciales
**Salidas:** Matriz de Trazabilidad y Requisitos Formales

**Área de proceso:** Ingeniería de Requisitos  
**Nombre del proceso:** Especificación y trazabilidad de requerimientos  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.

|Nombre del documento|Ubicación|
|---|---|
|Minuta de Entrevista|[[01-Linea_Base/05-Minuta_Entrevista|05-Minuta_Entrevista]]|
|Acuerdos del Cliente|[[01-Linea_Base/03-Acuerdos_Cliente|03-Acuerdos_Cliente]]|
|Propuesta Recuperada|[[01-Linea_Base/02-Propuesta_Recuperada|02-Propuesta_Recuperada]]|
|Matriz de Trazabilidad de Requisitos (RTM)|[[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]]|
|REQ-01 Carga de Imagen del Cliente|[[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|01-REQ-01_Carga_Imagen]]|
|REQ-02 Previsualización de Marco Interactivo|[[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|05-REQ-02_Previsualizacion_Marco]]|
|REQ-03 Generación de Marcos 3D (Pillow)|[[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/06-REQ-03_Generacion_Marcos_3D|06-REQ-03_Generacion_Marcos_3D]]|
|REQ-04 Catálogo de Marcos Disponibles|[[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos|02-REQ-04_Catalogo_Marcos]]|
|REQ-05 Filtrado de Catálogo en Servidor|[[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|03-REQ-05_Filtrado_Catalogo]]|
|REQ-06 Datos del Catálogo de Marcos|[[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/04-REQ-06_Datos_Catalogo|04-REQ-06_Datos_Catalogo]]|

---

## Proceso

### 1. Capturar la solicitud de requisito

**Actualmente:**

- El cliente o los programadores sugieren nuevas funciones de palabra, mediante conversaciones informales de WhatsApp o correos no estructurados.
- Las solicitudes se pierden, se olvidan o se implementan directamente sin control, provocando que el alcance original del proyecto crezca de forma desmedida (Scope Creep) y que las estimaciones de tiempo y costo queden obsoletas.

**NT-1:** La captura informal de requisitos es la principal causa de descontrol en el alcance y retrasos en proyectos de software. Conforme a CMMI-DEV v1.3 (área de proceso Gestión de Requisitos - REQM), es fundamental centralizar, identificar de manera única y documentar formalmente cada petición. El libro clásico de Regan (2002) sostiene que formalizar los requisitos de entrada de manera sistemática evita malentendidos comunicativos entre el cliente y el equipo de desarrollo, reduciendo las desviaciones en el alcance del proyecto. Se propone registrar toda solicitud en un archivo inicial en la carpeta de pendientes con un ID estructurado único.

**Propuesta:**

- El Analista de Requerimientos captura toda nueva solicitud en una nota individual dentro del directorio de pendientes `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/`.
- Cada nota se nombra usando un prefijo consecutivo estructurado: `REQ-XXX` (ejemplo: `07-REQ-07_Marcos_Dobles.md`).
- El Analista de Requerimientos vincula el origen del requerimiento con la solicitud de cambio (Change Request) de la cual proviene:
    - Las solicitudes de cambio pendientes de especificación se registran físicamente en:
        - [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/07-REQ-07_Marcos_Dobles|REQ-07 Marcos Dobles]] (derivado de la solicitud de cambio [[07-Control/01-Ingenieria_Control/08-CR-01_Marcos_Dobles|CR-01 Marcos Dobles]]).
        - [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/08-REQ-08_Tipo_Vidrio|REQ-08 Tipo de Vidrio]] (derivado de la solicitud de cambio [[07-Control/01-Ingenieria_Control/09-CR-02_Tipos_Vidrio|CR-02 Tipos de Vidrio]]).
        - [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/09-REQ-09_Maria_Luisa|REQ-09 María Luisa]] (derivado de la solicitud de cambio [[07-Control/01-Ingenieria_Control/10-CR-03_Maria_Luisa|CR-03 María Luisa]]).
        - [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria|REQ-10 Pantalla Secundaria]] (derivado de la solicitud de cambio [[07-Control/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]]).
- La nota inicial debe registrar como mínimo:
    - ID del Requisito.
    - Nombre del Requisito.
    - Origen / Solicitante (Cliente, Programador, etc.) y link a su Change Request relacionado.
    - Descripción informal de la petición.
    - Estado inicial: "Pendiente".

---

### 2. Especificar y estructurar el requisito

**Actualmente:**

- Los requisitos se describen de manera vaga o ambigua (por ejemplo: "el sistema debe hacer zoom a la imagen de forma interactiva").
- No se definen criterios claros para saber si el requisito está realmente cumplido, lo que provoca que los programadores implementen lógica incorrecta y que los analistas de pruebas no puedan validar de forma objetiva la funcionalidad.

**NT-2:** La ambigüedad en los requerimientos se traduce en defectos de diseño y pruebas inservibles. El SWEBOK v4 (capítulo de Requisitos de Software) enfatiza que los requisitos deben ser verificables, coherentes y medibles. La utilización de plantillas con criterios BDD (Behavior-Driven Development: Dado/Cuando/Entonces) permite eliminar las interpretaciones subjetivas y proporciona una base sólida para el diseño de pruebas de aceptación. Se propone que todo requisito cuente con criterios de aceptación explícitos, estimación de esfuerzo y prioridad clara antes de continuar.

**Propuesta:**

- El Analista de Requerimientos edita el archivo `REQ-XXX` en la carpeta de pendientes para detallarlo técnicamente, utilizando de referencia la estructura y completitud de los requisitos ya aprobados:
    - [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01 Carga de Imagen]] (criterios de carga de formatos JPG/PNG, límite de 10 MB y compresión local).
    - [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02 Previsualización Marco]] (lógica del visor y margen del marco interactivo).
    - [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/06-REQ-03_Generacion_Marcos_3D|REQ-03 Generación Marcos 3D]] (criterios de superposición y renderizado del marco).
    - [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos|REQ-04 Catálogo de Marcos]] (catálogo de marcos disponibles).
    - [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05 Filtrado Catálogo]] (filtrado por modelo, color y ancho).
    - [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/04-REQ-06_Datos_Catalogo|REQ-06 Datos Catálogo]] (criterios de persistencia de datos de catálogo).
- Aplica de forma estricta la plantilla de especificación, la cual debe incluir obligatoriamente las siguientes secciones:
    - **1. Descripción General:** "Como [Rol], quiero [Acción] para [Beneficio]".
    - **2. Reglas de Negocio:** Restricciones de negocio detalladas (por ejemplo: formato de imagen, tamaño de archivo, límites).
    - **3. Precondiciones:** Estado inicial del sistema requerido.
    - **4. Flujo Principal (Happy Path):** Pasos secuenciales numerados para el camino exitoso.
    - **5. Flujos Alternativos y Flujos de Excepción:** Tablas estructuradas para variaciones y manejo de errores.
    - **6. Criterios de Aceptación (formato BDD):** Tabla estructurada con las columnas:
        - **CA-ID:** Identificador único (ejemplo: CA-01).
        - **Dado:** [Contexto inicial del sistema].
        - **Cuando:** [Acción ejecutada por el actor].
        - **Entonces:** [Resultado esperado y respuesta del sistema].
    - **7. Restricciones Técnicas y Dependencias.**
    - **8. Trazabilidad:** Links directos a Casos de Prueba y Change Requests.

---

### 3. Validar y aprobar el requisito con el Product Owner

**Actualmente:**

- Se asume que el cliente desea la funcionalidad tal como el equipo la interpretó internamente.
- No se solicita una validación o aprobación formal. Al final del desarrollo, el cliente rechaza el entregable porque "no era lo que tenía en mente", generando pérdidas considerables de tiempo y fricciones.

**NT-3:** La validación formal de requisitos es un mecanismo de gobernanza crítico en la ingeniería de software. Daniel Galin establece que la aprobación formal del cliente actúa como un contrato técnico que delimita la responsabilidad del equipo de calidad. Regan (2002) sustenta que la confirmación explícita por escrito (ya sea por correo electrónico, minuta de reunión firmada o confirmación por mensajería institucional) es la única evidencia objetiva de alineación de expectativas, protegiendo al proyecto de modificaciones imprevistas sin la debida compensación de esfuerzo.

**Propuesta:**

- El Analista de Requerimientos presenta la especificación detallada del requisito al Product Owner (o cliente).
- Para los requisitos iniciales del proyecto se valida su consistencia contra el [[01-Linea_Base/06-Contrato_Desarrollo|Contrato de Desarrollo]] original.
- Para los requisitos adicionales, se valida el impacto técnico y estimación contra su correspondiente solicitud de cambio:
    - Ejemplo: Validar [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/07-REQ-07_Marcos_Dobles|REQ-07]] contra el alcance y viabilidad planteados en [[07-Control/01-Ingenieria_Control/08-CR-01_Marcos_Dobles|CR-01 Marcos Dobles]].
- Resuelven dudas y ajustan los criterios de aceptación en conjunto de ser necesario.
- Se solicita una aprobación explícita por escrito (confirmación por correo electrónico o captura de mensaje del canal oficial).
- Se adjunta la captura de pantalla o el texto íntegro de la confirmación formal directamente en la sección "Evidencia de Aprobación" del archivo `REQ-XXX`.
- El estado del requisito se actualiza formalmente a "Aprobado".

---

### 4. Línea Base de Requisitos y Trazabilidad

**Actualmente:**

- Los requisitos aprobados se guardan mezclados con los pendientes. No se sabe con certeza cuáles están listos para programarse y cuáles están en revisión.
- No se realiza un mapeo para saber qué requisitos se relacionan con qué casos de prueba o con qué tareas de desarrollo, perdiéndose la trazabilidad completa en el ciclo de vida.

**NT-4:** La segregación física de los artefactos basada en su estado es un control de configuración fundamental reconocido por CMMI-DEV v1.3 (área de proceso Gestión de Configuración - CM). Mover un archivo aprobado de una carpeta de "Pendientes" a una de "Aprobados" impide que el equipo trabaje sobre especificaciones inestables. Además, el SWEBOK v4 considera la trazabilidad bidireccional (desde la fuente hasta el código y las pruebas) un pilar para el análisis de impacto y el control de cambios. Se propone la actualización obligatoria de la Matriz de Trazabilidad RTM al incorporar cualquier requisito a la Línea Base.

**Propuesta:**

- Una vez aprobado el requisito por el Product Owner, el Analista de Requerimientos mueve físicamente el archivo `REQ-XXX` desde la carpeta de pendientes `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/` a la carpeta de aprobados `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/`.
- El Analista de Requerimientos actualiza de inmediato la Matriz de Trazabilidad de Requisitos (RTM) ([[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]]) mapeando y documentando las siguientes relaciones:
    1. **Fuente del Requisito:** Enlazar al [[01-Linea_Base/06-Contrato_Desarrollo|Contrato de Desarrollo]] para requerimientos originales, o al Change Request relacionado (ejemplo: [[07-Control/01-Ingenieria_Control/08-CR-01_Marcos_Dobles|CR-01]] para REQ-07) para requerimientos nuevos.
    2. **Diseño Relacionado:** Enlazar a la especificación técnica en `03-Diseño/01-Ingenieria_Arquitectura/`:
        - [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes|STD-04 Diagrama de Componentes]] (para REQ-01).
        - [[03-Diseño/01-Ingenieria_Arquitectura/02-STD-05_Flujo_Sistema|STD-05 Flujo del Sistema]] (para REQ-02).
        - [[03-Diseño/01-Ingenieria_Arquitectura/03-STD-06_Modelo_Datos|STD-06 Modelo de Datos]] (para REQ-03 y REQ-06).
        - [[03-Diseño/01-Ingenieria_Arquitectura/04-STD-07_Arquitectura_Python|STD-07 Arquitectura Python]] (para REQ-04 y REQ-05).
    3. **Casos de Prueba de Verificación:** Enlazar a los casos de prueba correspondientes en `05-Pruebas/01-Ingenieria_Pruebas/`:
        - [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/01-CP-01_JPG_valida|CP-01 JPG Valida]], [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/02-CP-02_Archivo_invalido|CP-02 Archivo Invalido]], [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/03-CP-03_Imagen_grande|CP-03 Imagen Grande]] (para REQ-01).
        - [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/01-CP-04_Carga_catalogo|CP-04 Carga Catálogo]], [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/02-CP-05_Filtro_modelo|CP-05 Filtro Modelo]], [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/03-CP-06_Filtro_color|CP-06 Filtro Color]], [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/04-CP-07_Filtro_ancho|CP-07 Filtro Dimensiones]] (para REQ-04, REQ-05 y REQ-06).
        - [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/01-CP-08_Marco_simple|CP-08 Marco Simple]], [[05-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/05-CP-12_Proporciones|CP-12 Proporciones]] (para REQ-02 y REQ-03).
- **Destino y Uso Operativo de los Requisitos Aprobados:**
    *   **1. Desarrollo e Implementación (Fase 04):** Actúa como el insumo de entrada (*Entry Criteria*) y orden de trabajo oficial para el **Líder de Desarrollo e Implementación**. Este utilizará el archivo `REQ-XXX` aprobado dentro de `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/` como referencia definitiva para la construcción y codificación de la funcionalidad en el repositorio Git (conforme al proceso [[04-Codificacion/00-PROC-04_Codificacion|PROC-04 Codificación]]), respetando las reglas de negocio y restricciones técnicas descritas.
    *   **2. Diseño y Cobertura de Pruebas (Fase 05):** Sirve como la especificación funcional definitiva para el **Analista de Verificación y Pruebas**. Este rol mapeará los criterios de aceptación BDD (Dado/Cuando/Entonces) del requerimiento aprobado para diseñar los Casos de Prueba (CP-XXX) y asegurar que la cobertura funcional en el Plan Maestro de Pruebas ([[05-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02]]) sea del 100.00%.
    *   **3. Control de Configuración y Cambios (Fase 07):** Cualquier modificación posterior a un requisito ubicado en la carpeta de aprobados (que ya forma parte de la Línea Base estable) queda estrictamente regulada. Para realizar cualquier alteración o eliminación se debe emitir una Solicitud de Cambio formal ([[07-Control/03-PROC-08_Control_Cambios|PROC-08 Control de Cambios]]) por parte del **Analista de Control y Cambios**, prohibiéndose modificaciones directas sobre el archivo aprobado sin el debido análisis de impacto y autorización.
- Una vez registrada su trazabilidad y uso, el requisito entra formalmente en la Línea Base estable del proyecto y queda oficialmente en estado "Aprobado".

---

## Justificación de Mejoras

**NT-1 — Registro y Centralización de Requisitos**  
La captura formal evita el "Scope Creep". CMMI-DEV (REQM) y Regan (2002) enfatizan la necesidad de tener un control estricto de entradas desde el inicio del ciclo de vida para evitar desviaciones.

**NT-2 — Especificación y Criterios BDD**  
El uso del formato Dado/Cuando/Entonces elimina ambigüedades e interpretaciones subjetivas. SWEBOK v4 requiere que los requisitos sean cuantificables y verificables de manera objetiva para el diseño de pruebas.

**NT-3 — Validación Formal y Evidencia**  
La confirmación explícita por escrito del cliente previene malentendidos y sirve de respaldo contractual. Galin resalta que el aseguramiento de la calidad contractual exige la validación formal y aprobación explícita de los requisitos.

**NT-4 — Segregación y Matriz de Trazabilidad**  
El control de configuración físico (`00-Pendientes` -> `01-Aprobados`) y la actualización de la RTM garantizan trazabilidad bidireccional, previniendo el desarrollo sobre requisitos inestables según CMMI-DEV (CM).

---

## Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Requisitos de Software.

[2] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Estructuración de Requisitos e Independencia).

[3] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Calidad Contractual e Infraestructura).

[4] CMMI-DEV v1.3. _CMMI para Desarrollo_, Software Engineering Institute. Áreas de proceso: Gestión de Requisitos (REQM) y Gestión de Configuración (CM).

[5] Matriz de Trazabilidad de Requisitos (RTM). [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]]