# Proceso de Codificación — XookTech
**Responsable:** Líder de Desarrollo e Implementación
**Entradas:** Diseño del Sistema y Estándar de Codificación
**Salidas:** Módulos de Código Fuente Verificados

**Área de proceso:** Desarrollo de Software  
**Nombre del proceso:** Codificación de funcionalidades del sistema  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.

|Nombre del documento|Ubicación|
|---|---|
|Documento de requisitos|[PENDIENTE: definir ruta]|
|Plan de diseño|[PENDIENTE: definir ruta]|
|Esquema de base de datos|[PENDIENTE: definir ruta]|
|Estándar de Codificación de XookTech|[[04-Codificacion/Documentos_Apoyo/02-Formatos/FOR-04-01_Estandar_Codificacion|FOR-04-01]]|
|Lista de Verificación de Codificación|[[04-Codificacion/Documentos_Apoyo/02-Formatos/CL-04-01_Verificacion_Codificacion|CL-04-01]]|
|Registro de Tareas de Desarrollo|[[04-Codificacion/Documentos_Apoyo/01-Registros/REG-04-01_Tareas_Desarrollo|REG-04-01]]|

---

## Proceso

### 1. Recibir la tarea

**Actualmente:**

- El líder del proyecto le informa al programador de manera verbal sobre el módulo o funcionalidad que se necesita desarrollar.
- No existe un registro escrito de lo que se pidió ni de cuándo se pidió.

**NT-1:** La comunicación verbal no deja evidencia de lo que se acordó. Si el programador entiende algo diferente a lo que se pidió, no hay manera de verificar quién tuvo razón. El SWEBOK v3 (capítulo de Construcción del Software) señala que toda tarea de construcción debe poder rastrearse hasta un requisito o decisión documentada. Se propone que cada tarea quede registrada por escrito antes de comenzar a codificar.

**Propuesta:**

- El líder del proyecto registra la tarea por escrito en el Registro de Tareas de Desarrollo ([[04-Codificacion/Documentos_Apoyo/01-Registros/REG-04-01_Tareas_Desarrollo|REG-04-01]]).
- La tarea debe incluir como mínimo:
    - Folio de la tarea (TAR-YYYY-NNN).
    - Prioridad (Baja/Media/Alta).
    - Folio del requisito relacionado (REQ-XXX).
    - Nombre de la funcionalidad.
    - Descripción breve de qué debe hacer.
    - Fecha en que se asignó.
    - Nombre del programador responsable.
- El programador confirma que entendió la tarea antes de comenzar. Si tiene dudas, las resuelve en este momento, no durante la codificación.

---

### 2. Revisar la documentación disponible

**Actualmente:**

- El programador recibe el plan de diseño si existe, el documento de requisitos si existe, y el esquema de base de datos si existe, pero sin diagramas.
- Lo más común es que ninguno de estos documentos exista y el programador implemente la funcionalidad a su criterio.

**NT-2:** Comenzar a codificar sin revisar lo que existe aumenta el riesgo de repetir trabajo, romper funcionalidades ya desarrolladas, o construir algo que no corresponde con lo que el cliente pidió. IEEE 12207:2017 (proceso de implementación del software) establece que antes de codificar se deben verificar que los insumos necesarios están disponibles y son suficientes. Se propone una revisión mínima antes de escribir la primera línea de código.

**Propuesta:**

- El programador revisa si existe alguno de los siguientes documentos antes de comenzar:
    - Documento de requisitos: define _qué_ debe hacer la funcionalidad.
    - Plan de diseño: define _cómo_ está estructurado el sistema.
    - Esquema de base de datos: define las tablas y relaciones que aplican.
- Si alguno de estos documentos no existe, el programador lo anota en la tarea y lo comunica al líder del proyecto.
- El líder del proyecto decide si se continúa sin el documento o si primero se genera uno, aunque sea breve.
- No se inicia la codificación hasta que el programador y el líder del proyecto estén de acuerdo en los puntos que no están claros.

---

### 3. Configurar el repositorio

**Actualmente:**

- El programador crea un repositorio al inicio del proyecto si así lo decide.
- El acceso al repositorio se comparte con el resto del equipo en algún momento sin un momento definido para hacerlo.
- No en todos los proyectos se crea un repositorio.

**NT-3:** Un repositorio es la única herramienta que permite saber qué cambió, cuándo cambió y quién lo cambió. Sin él, cualquier error en el código puede ser irreversible y colaborar entre programadores se vuelve un problema manual. SWEBOK v3 (sección de Gestión de la Configuración del Software) considera el control de versiones un requisito básico de cualquier proceso de construcción de software profesional. Se propone que el repositorio sea obligatorio y que se configure al inicio de cada proyecto.

**Propuesta:**

- Al inicio de cualquier proyecto, el líder del proyecto o el programador asignado crea el repositorio en la plataforma definida por el equipo.
- Las credenciales y accesos críticos se almacenan en el gestor de contraseñas privado de XookTech, con acceso restringido.
- El repositorio se comparte con todos los integrantes del equipo antes de que cualquiera escriba código.
- Cada funcionalidad se desarrolla en una rama separada del repositorio. El nombre de la rama debe indicar qué se está desarrollando. Ejemplo: `feature/TAR-2025-001-registro-usuarios`.
- La rama principal del repositorio debe mantenerse siempre en un estado funcional. No se sube código que rompa el sistema a la rama principal.

---

### 4. Revisar el código existente antes de acoplarse

**Actualmente:**

- El programador revisa el código que ya existe y se adapta a él, o comienza de cero si es un proyecto nuevo.
- No hay un criterio definido para saber hasta dónde revisar antes de empezar.

**NT-4:** Acoplarse a código sin entenderlo genera errores de integración difíciles de depurar. Una revisión previa reduce el tiempo total del desarrollo aunque aparente retrasarlo al inicio.

**Propuesta:**

- Si el proyecto ya tiene código:
    - El programador identifica qué partes del sistema existente están relacionadas con la funcionalidad que va a desarrollar.
    - Si no entiende alguna parte, lo consulta con quien la desarrolló o con el líder del proyecto antes de continuar.
- Si el proyecto es nuevo:
    - El programador revisa el Estándar de Codificación de XookTech ([[04-Codificacion/Documentos_Apoyo/02-Formatos/FOR-04-01_Estandar_Codificacion|FOR-04-01]]) y lo sigue desde el primer archivo.

---

### 5. Codificar la funcionalidad

El programador desarrolla la funcionalidad asignada. Dependiendo de lo que implique, realiza una o varias de las **Actividades Comunes** descritas más adelante en este documento.

Durante la codificación:

- El programador sigue estrictamente el Estándar de Codificación de XookTech ([[04-Codificacion/Documentos_Apoyo/02-Formatos/FOR-04-01_Estandar_Codificacion|FOR-04-01]]), priorizando el uso de `camelCase`, nombres explícitos en español y funciones autodescriptivas.
- Cada vez que termina una parte significativa del trabajo, sube los cambios al repositorio con un mensaje que describa qué se hizo.

**NT-5:** Los mensajes de confirmación vagos como "cambios" o "actualización" no aportan información útil para el equipo. IEEE 12207:2017 recomienda que los registros de cambio sean comprensibles y trazables. Un mensaje descriptivo permite entender el historial del proyecto sin tener que leer todo el código.

Ejemplos de mensajes aceptables:

- `"TAR-2025-001: Se agrega validación de correo en el formulario de registro"`
- `"TAR-2025-002: Se corrige error al guardar pedidos con productos sin precio"`

Ejemplos de mensajes que no aportan:

- `"cambios"`
- `"fix"`
- `"avance"`
    
- Si durante la codificación el programador encuentra algo que no está claro en los requisitos o en el diseño, detiene el trabajo y lo consulta antes de continuar.
    

---

### 6. Verificar la tarea antes de integrarla

**Actualmente:**

- No existe ninguna revisión hasta que la funcionalidad está completamente terminada.
- La revisión la realiza el mismo programador que desarrolló el código.

**NT-6:** Revisar el propio código tiene un límite: quien lo escribió ya sabe cómo funciona y tiende a leerlo como quiso que fuera, no como está escrito. IEEE 1028-2008 (Estándar para Revisiones e Inspecciones de Software) establece que la revisión por otra persona es la práctica más efectiva para detectar defectos antes de que lleguen al cliente. Se propone una revisión mínima antes de integrar cualquier funcionalidad.

**Propuesta:**

- Cuando el programador considera que terminó la funcionalidad, la verifica con la Lista de Verificación de Codificación ([[04-Codificacion/Documentos_Apoyo/02-Formatos/CL-04-01_Verificacion_Codificacion|CL-04-01]]).
- La lista debe revisar como mínimo:
    - Que el código hace lo que la tarea pedía.
    - Que no rompe funcionalidades que ya existían.
    - Que sigue el Estándar de Codificación del equipo.
    - Que los nombres de variables, funciones y archivos son descriptivos, explícitos (sin acotamientos) y consistentes.
- Se requiere una **Revisión por Pares** (Peer Review). Otro integrante del equipo revisa el código, anota sus observaciones en el formato CL-04-01 y el programador las corrige antes de continuar.

**NT-7:** Cuando el equipo es de una sola persona, revisar el propio código al día siguiente de haberlo escrito — con la mente fresca — es una alternativa válida reconocida en la práctica de ingeniería de software. No es lo mismo que no revisar nada.

---

### 7. Integrar el código a la rama principal

- Una vez verificada la funcionalidad, el programador integra su rama al repositorio principal.
- El programador verifica que el sistema completo sigue funcionando después de la integración.
- Si algo se rompe durante la integración, se corrige antes de continuar con otra tarea.
- Se actualiza el estado de la tarea en el Registro de Tareas de Desarrollo ([[04-Codificacion/Documentos_Apoyo/01-Registros/REG-04-01_Tareas_Desarrollo|REG-04-01]]) indicando que está "Listo".

---

## Actividades Comunes

Las siguientes actividades se realizan con frecuencia dentro de la codificación. No todas aplican a cada tarea; el programador realiza las que correspondan según lo que pida la funcionalidad.

---

### A. Migraciones de base de datos

Una migración es un archivo que describe un cambio en la estructura de la base de datos — crear una tabla, agregar una columna, modificar un tipo de dato, etc. — de forma que ese cambio quede registrado y pueda aplicarse en cualquier entorno del equipo.

1. Antes de crear una migración, el programador revisa el esquema de base de datos actual para verificar que el cambio no entra en conflicto con algo que ya existe.
2. Se crea el archivo de migración siguiendo el Estándar de Codificación de XookTech.
3. Se agrega al inicio del archivo, en forma de comentario, el nombre del responsable, la fecha y la tarea que motivó la migración.
4. Se ejecuta la migración en el entorno de desarrollo local y se verifica que funcionó correctamente.
5. Si la migración afecta datos que ya existen, se documenta qué datos se ven afectados y de qué forma.
6. Se sube la migración al repositorio junto con el resto del código de la tarea.

---

### B. Operaciones sobre la base de datos (consultas, inserciones, actualizaciones, eliminaciones)

1. El programador identifica qué tablas y relaciones están involucradas en la operación que necesita.
2. Se escribe la lógica de acceso a datos siguiendo el Estándar de Codificación.
3. Se prueban las operaciones en el entorno local con datos de prueba antes de considerarlas listas.
4. Se verifica que las operaciones no afecten datos que no deberían tocarse.

**NT-8:** Colocar la lógica de acceso a datos en cualquier parte del código hace que los proyectos sean difíciles de mantener y de corregir. Se recomienda que toda esta lógica esté concentrada en una capa específica del sistema — modelos o repositorios, según el patrón que el equipo defina — y no dispersa en vistas, controladores u otros archivos. SWEBOK v3 (Diseño del Software) lo incluye como parte del principio de separación de responsabilidades.

---

### C. Creación de modelos

Un modelo es la representación en código de una entidad del sistema — un usuario, un pedido, un producto, etc.

1. Se revisa el esquema de base de datos o el documento de diseño para identificar qué atributos tiene the entidad.
2. Se crea el archivo del modelo siguiendo el Estándar de Codificación.
3. Se definen los atributos del modelo según lo que indica el diseño (usando `camelCase` para propiedades).
4. Se agregan las validaciones necesarias. Ejemplos: que el correo tenga formato válido, que el nombre no esté vacío, que el precio sea mayor a cero.
5. Se agrega al inicio del archivo, en forma de comentario, el nombre del responsable, la fecha y la tarea relacionada.

---

### D. Creación de páginas o vistas

1. El programador revisa si existe un diseño o prototipo de la página. Si no existe, lo consulta con el líder del proyecto antes de comenzar.
2. Se crea el archivo de la vista siguiendo la estructura del proyecto y el Estándar de Codificación.
3. Se agrega al inicio del archivo, en forma de comentario, el nombre del responsable, la fecha y la tarea relacionada.
4. Se prueba la página en el entorno local antes de integrarla al repositorio.

---

### E. Conexión entre la interfaz y el servidor mediante peticiones asíncronas

1. El programador identifica qué operación necesita hacer la interfaz — obtener datos, enviar un formulario, actualizar un registro, etc.
2. Se define o se revisa la ruta del servidor que atiende esa operación.
3. Se implementa la llamada desde la interfaz al servidor.
4. Se manejan los casos de error:
    - ¿Qué se muestra si el servidor no responde?
    - ¿Qué se muestra si los datos enviados no son válidos?
    - ¿Qué se muestra si la operación fue exitosa?
5. Se prueba la conexión con datos reales en el entorno local antes de integrar.

---

### F. Creación y configuración de rutas del servidor

1. Se identifica la operación que la ruta debe atender.
2. Se define el tipo de petición que usará la ruta (GET, POST, PUT, DELETE).
3. Se crea la ruta en el archivo de configuración de rutas del sistema.
4. Se conecta la ruta con el controlador o la función que la atiende.
5. Se prueba que la ruta responde correctamente en el entorno local antes de integrarla.

---

## Justificación de Mejoras

**NT-1 — Registro escrito de tareas**  
Las instrucciones verbales no generan evidencia. SWEBOK v3 (Construcción del Software) establece que la construcción debe ser trazable a los requisitos o decisiones que la originaron.

**NT-2 — Revisión de documentación antes de codificar**  
Codificar sin entender completamente lo que se pide es la causa más frecuente de retrabajo. IEEE 12207:2017 requiere que los insumos de entrada estén verificados antes de iniciar la construcción.

**NT-3 — Repositorio obligatorio desde el inicio**  
El control de versiones no es opcional. SWEBOK v3 (Gestión de la Configuración del Software) lo trata como un componente básico. El uso de un gestor de contraseñas privado protege la infraestructura del equipo.

**NT-4 — Revisión del código existente antes de acoplarse**  
Acoplarse a código sin entenderlo genera errores de integración costosos.

**NT-5 — Mensajes de confirmación descriptivos**  
El historial del repositorio es la memoria del proyecto. IEEE 12207:2017 requiere que los registros de cambio sean comprensibles y rastreables (incluyendo folios de tarea).

**NT-6 y NT-7 — Verificación antes de integrar**  
IEEE 1028-2008 establece que la revisión del código por otra persona es la práctica más efectiva para detectar defectos. La inclusión de estándares de nombres explícitos y autodescriptivos facilita esta revisión.

**NT-8 — Concentrar el acceso a datos en una capa específica**  
La separación de responsabilidades (SWEBOK v3) reduce de forma significativa el costo de mantenimiento a largo plazo.

---

## Referencias

[1] SWEBOK v3.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2014. Capítulos consultados: Construcción del Software, Gestión de la Configuración del Software, Diseño del Software.

[2] IEEE 12207:2017. _Ingeniería de Sistemas y Software — Procesos del Ciclo de Vida del Software_. IEEE/ISO.

[3] IEEE 1028-2008. _Estándar para Revisiones e Inspecciones de Software_. IEEE.

[4] Estándar de Codificación de XookTech. [[04-Codificacion/Documentos_Apoyo/02-Formatos/FOR-04-01_Estandar_Codificacion|FOR-04-01]]
[5] Lista de Verificación de Codificación de XookTech. [[04-Codificacion/Documentos_Apoyo/02-Formatos/CL-04-01_Verificacion_Codificacion|CL-04-01]]
[6] Registro de Tareas de Desarrollo. [[04-Codificacion/Documentos_Apoyo/01-Registros/REG-04-01_Tareas_Desarrollo|REG-04-01]]