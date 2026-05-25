# Proceso de Recuperación de la Línea Base — XookTech
**Responsable:** Analista de Requerimientos
**Entradas:** Acuerdos del Cliente e Información Inicial
**Salidas:** Línea Base del Proyecto Certificada

**Área de proceso:** Recuperación de la Línea Base  
**Nombre del proceso:** Recuperación de la línea base del proyecto  
**Basado en:** Metodología Deming (Ciclo PDCA: Planear, Hacer, Verificar, Actuar)  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.

|Nombre del documento|Ubicación|
|---|---|
|Acta de Inicio|[[09-Notes/01-Linea_Base-Original/01-Acta_Inicio|01-Acta_Inicio]]|
|Propuesta Recuperada|[[09-Notes/01-Linea_Base-Original/02-Propuesta_Recuperada|02-Propuesta_Recuperada]]|
|Acuerdos del Cliente|[[09-Notes/01-Linea_Base-Original/03-Acuerdos_Cliente|03-Acuerdos_Cliente]]|
|Guía de Entrevista PO|[[09-Notes/01-Linea_Base-Original/04-Guia_Entrevista_PO|04-Guia_Entrevista_PO]]|
|Minuta de Entrevista|[[09-Notes/01-Linea_Base-Original/05-Minuta_Entrevista|05-Minuta_Entrevista]]|
|Contrato de Desarrollo|[[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|06-Contrato_Desarrollo]]|

---

## Proceso

### 1. Planear la entrevista y estructurar el cuestionario (Planear)

**Actualmente:**

- Las reuniones de levantamiento de requerimientos y entrevistas con el Product Owner se agendaban y ejecutaban de palabra, sin contar con un cuestionario estructurado o guía de preguntas diseñada de forma previa.
- Esto ocasionaba que las sesiones de entrevista se dispersaran en temas comerciales no prioritarios, y que al concluir se tuvieran múltiples vacíos de información técnica y de negocio que retrasaban el arranque del diseño.

**NT-1:** Confiar la elicitación técnica a una conversación libre y sin estructura previa produce vacíos de información sumamente costosos e irrecuperables. El SWEBOK v4 (Área de Requisitos) [1] establece que la elicitación de requisitos exige un enfoque planificado, reproducible y el uso de técnicas estructuradas de levantamiento. G. O. Regan (2002) [3] argumenta que planificar sistemáticamente el levantamiento inicial mitiga de raíz los errores de comunicación y formaliza las asunciones técnicas de la Fase 01. Se propone diseñar un cuestionario estructurado y agendar la sesión por canales escritos.

**Propuesta:**

- El Analista de Requerimientos planifica la reunión de levantamiento con el Product Owner agendándola vía correo electrónico o mensajería oficial del equipo.
- Diseña y estructura previamente la [[09-Notes/01-Linea_Base-Original/04-Guia_Entrevista_PO|Guía de Entrevista PO (04-Guia_Entrevista_PO)]], delimitando las preguntas clave sobre dimensiones físicas, formatos y lógica de marcos.
- Crea y formaliza el [[09-Notes/01-Linea_Base-Original/01-Acta_Inicio|Acta de Inicio (01-Acta_Inicio)]] para detallar el propósito y asegurar la participación equitativa de los 5 roles asignados.

---

### 2. Ejecutar la entrevista y documentar los acuerdos preliminares (Hacer)

**Actualmente:**

- Durante la entrevista técnica no se usaba una plantilla formal para la toma de apuntes, registrando las respuestas en hojas sueltas o minutas vagas que posteriormente se perdían o se interpretaban subjetivamente.
- Los compromisos funcionales y comerciales de alcance se tomaban mediante conversaciones dispersas de mensajería (WhatsApp) sin ningún tipo de sustento formal o minuta firmada.

**NT-2:** El almacenamiento informal de compromisos en canales no oficiales sin minutas estructuradas compromete la trazabilidad e integridad del proyecto. Daniel Galin [4] señala que el aseguramiento de la calidad contractual exige la consolidación formal de todas las características y decisiones técnicas acordadas con el cliente. Se propone consolidar las respuestas en una minuta y redactar los Acuerdos del Cliente formales.

**Propuesta:**

- El Analista de Requerimientos ejecuta la entrevista apegándose a la guía estructurada y documenta textualmente las respuestas en la [[09-Notes/01-Linea_Base-Original/05-Minuta_Entrevista|Minuta de Entrevista (05-Minuta_Entrevista)]].
- Concentra todos los compromisos funcionales y comerciales detallados con el Product Owner en el documento estructurado [[09-Notes/01-Linea_Base-Original/03-Acuerdos_Cliente|Acuerdos del Cliente (03-Acuerdos_Cliente)]], sirviendo de respaldo formal ante cambios imprevistos.

---

### 3. Realizar la ingeniería inversa documental para la propuesta recuperada (Verificar)

**Actualmente:**

- El proyecto heredado carecía de cualquier documentación de propuesta o alcance técnico inicial.
- El equipo de ingeniería heredaba el código fuente funcional del prototipo en CachyOS sin saber qué asunciones de negocio ni reglas de cálculo se planearon en un origen.

**NT-3:** Heredar un prototipo de software funcional sin un análisis documental ni punto de comparación inicial incrementa drásticamente los defectos de integración e inconsistencias. El estándar IEEE 12207:2017 [5] establece que el proceso de implementación del ciclo de vida exige analizar y verificar los insumos existentes. La ingeniería inversa documental para reconstruir una propuesta técnica formaliza las asunciones técnicas iniciales de OpenCV/Pillow, estableciendo la Línea Base de diseño. Se propone redactar la Propuesta Recuperada formal.

**Propuesta:**

- El Analista de Requerimientos analiza el prototipo funcional actual, detectando las rutas, vistas y tecnologías utilizadas (Flask/OpenCV/Pillow).
- Redacta de forma detallada la [[09-Notes/01-Linea_Base-Original/02-Propuesta_Recuperada|Propuesta Recuperada (02-Propuesta_Recuperada)]], documentando la arquitectura preliminar del sistema, la cotización estimada de esfuerzo y los casos de uso recuperados por ingeniería inversa.

---

### 4. Validar la Línea Base y certificar el Contrato (Actuar)

**Actualmente:**

- El contrato de desarrollo se firmaba sin comprobar su integridad técnica ni realizar un mapeo de paridad cruzado contra la propuesta recuperada.
- No existía un mecanismo formal de gobernanza para congelar y declarar estable la Línea Base inicial del proyecto, permitiendo la modificación de acuerdos desde el arranque.

**NT-4:** Firmar un contrato sin comprobar su viabilidad técnica y paridad contra la propuesta recuperada crea no conformidades graves de calidad contractual y desviaciones en el alcance del SGC. Lewis (2009) [2] insiste en que la inspección y verificación contractual al inicio del ciclo de vida (Ciclo PDCA) es el primer filtro de control de calidad para mitigar riesgos. Se propone realizar un mapeo cruzado de cláusulas frente a la propuesta recuperada antes de certificar la Línea Base.

**Propuesta:**

- El Analista de Requerimientos realiza una inspección y mapeo de las cláusulas y requerimientos de alcance especificados en el [[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|Contrato de Desarrollo (06-Contrato_Desarrollo)]] frente a la propuesta recuperada.
- Verifica que el entregable de la Línea Base inicial esté completo y compuesto por los 6 documentos de apoyo obligatorios (01 a 06).
- Declara oficialmente "Aprobada y Certificada" la Línea Base del proyecto, habilitando y autorizando el inicio de la ingeniería de requisitos en la Fase 02.

---

## Justificación de Mejoras

**NT-1 — Planificación y Cuestionario Estructurado**  
La elicitación sistemática evita vacíos de información y dispersión. SWEBOK v4 [1] y Regan (2002) [3] establecen que la planificación formal del levantamiento es crítica para mitigar errores comunicativos de arranque.

**NT-2 — Consolidación por Escrito y Minuta**  
Registrar los acuerdos en una minuta estructurada previene conflictos legales y de alcance. Daniel Galin [4] señala que la calidad contractual exige la consolidación formal por escrito de los acuerdos.

**NT-3 — Ingeniería Inversa Documental**  
Reconstruir la propuesta técnica mediante ingeniería inversa del código heredado formaliza el punto de partida técnico. IEEE 12207:2017 [5] requiere validar la suficiencia técnica de los insumos de inicio del ciclo de vida.

**NT-4 — Verificación Contractual y Línea Base (PDCA)**  
El mapeo de cláusulas antes de la firma actúa como control del alcance (Ciclo PDCA). Lewis (2009) [2] insiste en la auditoría del contrato como el primer filtro de calidad del SGC.

---

## Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Requisitos de Software.

[2] Lewis, W. E. (2009). _Software Testing and Continuous Quality Improvement_. USA: Auerbach Publications. (Ciclos PDCA y Calidad en Requisitos).

[3] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Estructura Organizativa de Calidad e Independencia).

[4] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Calidad Contractual e Infraestructura).

[5] IEEE 12207:2017. _Ingeniería de Sistemas y Software — Procesos del Ciclo de Vida del Software_.