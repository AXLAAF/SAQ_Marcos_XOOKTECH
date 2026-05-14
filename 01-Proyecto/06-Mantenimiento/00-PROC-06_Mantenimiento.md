# Proceso de Mantenimiento — XookTech

**Área de proceso:** Desarrollo de Software  
**Nombre del proceso:** Mantenimiento de sistemas en producción  
**Responsable:** Jefe de proyecto y programador asignado  
**Entradas:** Solicitud del cliente — ya sea un cambio, una nueva funcionalidad, o el reporte de un problema  
**Salidas:** Sistema actualizado en producción, con el cambio o corrección verificados y el cliente notificado  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.  
Los marcados como _[por crear]_ no existen todavía y se propone generarlos.

|Nombre del documento|Ubicación|
|---|---|
|Registro de solicitudes de mantenimiento|[[01-Proyecto/06-Mantenimiento/Documentos_Apoyo/01-Registros/REG-06-01_Solicitudes_Mantenimiento\|REG-06-01]]|
|Registro de errores reportados|[[01-Proyecto/06-Mantenimiento/Documentos_Apoyo/01-Registros/REG-06-02_Errores_Reportados\|REG-06-02]]|
|Lista de Verificación de Despliegue|[[01-Proyecto/08-Despliegue/Documentos_Apoyo/02-Formatos/CL-08-01_Verificacion_Despliegue\|CL-08-01]]|
|Plantilla de cotización de cambios|[[01-Proyecto/06-Mantenimiento/Documentos_Apoyo/02-Formatos/FOR-06-01_Cotizacion_Cambios\|FOR-06-01]]|

---

## El proceso se divide en dos rutas según el tipo de solicitud

- **Ruta A — Solicitud de cambio o nueva funcionalidad:** El cliente pide modificar algo que ya existe o agregar algo nuevo.
- **Ruta B — Reporte de problema:** El cliente reporta que algo no funciona correctamente o se comporta de forma inesperada.

Ambas rutas comparten el mismo punto de entrada: la notificación del cliente.

---

## Ruta A — Solicitud de cambio o nueva funcionalidad

### A.1. Recibir y registrar la solicitud

**Actualmente:**

- El cliente notifica el cambio o la nueva funcionalidad por mensaje directo o llamada.
- El jefe de proyecto anota lo que se pidió en el momento o después de la conversación.
- No existe un formato ni un lugar definido donde queden registradas estas solicitudes.

**NT-1:** Una solicitud recibida por mensaje o llamada y anotada de memoria o en cualquier cuaderno no es un registro confiable. Si el cliente pide algo, el jefe de proyecto lo interpreta de cierta forma y el programador lo implementa de otra, no hay documento al que acudir para resolver la diferencia. IEEE 12207:2017 (proceso de mantenimiento del software) establece que toda solicitud de modificación debe registrarse antes de analizarse o implementarse. Este registro es el punto de inicio de trazabilidad del mantenimiento.

**Propuesta:**

- Toda solicitud del cliente — sin importar si llega por mensaje, llamada o en persona — se registra en el Registro de solicitudes de mantenimiento ([[01-Proyecto/06-Mantenimiento/Documentos_Apoyo/01-Registros/REG-06-01_Solicitudes_Mantenimiento|REG-06-01]]) antes de hacer cualquier otra cosa.
- El registro debe incluir como mínimo:
    - Fecha en que se recibió.
    - Nombre del cliente y del sistema al que pertenece.
    - Descripción de lo que se pidió, en las palabras del cliente.
    - Quién recibió la solicitud.
- Si la solicitud llegó por llamada, se resume por escrito y se confirma con el cliente que el resumen es correcto antes de continuar.

---

### A.2. Analizar la solicitud y estimar el costo y tiempo

**Actualmente:**

- El jefe de proyecto determina el costo y el tiempo de realización.
- Esta estimación se le comunica al cliente en algún momento posterior a la solicitud, sin un plazo definido para hacerlo.
- No queda registro de qué se cotizó ni en qué términos se acordó.

**NT-2:** Una cotización verbal o por mensaje sin respaldo formal puede generar malentendidos cuando el cliente recibe el cobro o cuando el alcance del trabajo no queda claro. SWEBOK v3 (Gestión de la Ingeniería del Software) señala que los acuerdos de trabajo deben estar documentados para que ambas partes tengan la misma referencia. Esto no requiere un contrato formal en cada cambio, pero sí un registro mínimo del acuerdo.

**Propuesta:**

- Antes de comenzar cualquier trabajo, el jefe de proyecto le comunica al cliente por escrito:
    - Qué se va a hacer (basado en el registro de la solicitud).
    - Cuánto va a costar.
    - En cuánto tiempo estará listo.
- Se usa la Plantilla de cotización de cambios ([[01-Proyecto/06-Mantenimiento/Documentos_Apoyo/02-Formatos/FOR-06-01_Cotizacion_Cambios|FOR-06-01]]) para este comunicado.
- El trabajo no inicia hasta que el cliente confirme por escrito que está de acuerdo con el costo y el tiempo.
- La confirmación del cliente se guarda en el expediente del proyecto.

**NT-3:** Esperar confirmación escrita del cliente antes de iniciar puede parecer lento, pero protege al equipo de trabajar en algo que el cliente después rechaza pagar o que modifica sobre la marcha sin reconocer el costo adicional. En la práctica, si la comunicación con el cliente es por mensaje, una respuesta de "adelante" ya es un registro suficiente.

---

### A.3. Diseñar el cambio (cuando aplique)

**Actualmente:**

- El jefe de proyecto decide a criterio propio si se hace un diseño antes de programar.
- Lo más frecuente es que no se haga diseño y se pase directamente a la codificación.

**NT-4:** La falta de diseño no es un problema cuando el cambio es pequeño y bien entendido. Sí es un problema cuando el cambio afecta varias partes del sistema o cuando el programador que lo va a implementar no es el mismo que recibió la solicitud. SWEBOK v3 (Mantenimiento del Software) distingue entre cambios que requieren análisis de impacto y cambios menores que pueden implementarse directamente. Se propone definir un criterio mínimo para saber cuándo se necesita diseño y cuándo no.

**Propuesta:**

- Se hace diseño previo cuando el cambio cumple al menos una de estas condiciones:
    - Afecta más de un módulo del sistema.
    - Requiere modificar la base de datos.
    - Lo va a implementar alguien que no participó en la solicitud original.
- Si se hace diseño, el resultado queda registrado — aunque sea un diagrama simple o una descripción escrita de cómo va a funcionar — antes de iniciar la codificación.
- Si no se hace diseño, el jefe de proyecto deja anotado en el registro de la solicitud por qué se consideró innecesario.

---

### A.4. Implementar el cambio

- El programador asignado implementa el cambio siguiendo el Proceso de Codificación de XookTech ([ver Proceso de Codificación — XookTech]).
- Al terminar, el cambio pasa por la verificación definida en ese proceso antes de continuar.

---

### A.5. Desplegar el cambio a producción

- El cambio se despliega siguiendo el Proceso de Despliegue de XookTech ([ver Proceso de Despliegue — XookTech]).
- Se utilizan las pruebas definidas en ese proceso antes de notificar al cliente.

---

### A.6. Notificar al cliente y cerrar la solicitud

**Actualmente:**

- Se le avisa al cliente que el cambio ya está listo.
- No queda registro de cuándo se entregó ni de que el cliente lo recibió conforme.

**NT-5:** El cierre de una solicitud de mantenimiento es el punto donde el cliente confirma que lo que se entregó corresponde a lo que pidió. Sin ese cierre, cualquier problema posterior puede interpretarse como parte del mismo trabajo o como algo nuevo, generando conflicto sobre si tiene costo adicional. IEEE 12207:2017 (proceso de mantenimiento) incluye la confirmación del cliente como parte del cierre de cada solicitud.

**Propuesta:**

- Se notifica al cliente por escrito que el cambio está disponible en producción.
- Se le pide que revise lo que se entregó y confirme que corresponde a lo que solicitó.
- Si el cliente tiene observaciones, se registran como una nueva solicitud y se sigue el mismo proceso desde el paso A.1.
- Se marca la solicitud como cerrada en el Registro de solicitudes de mantenimiento con la fecha de cierre.

---

## Ruta B — Reporte de problema

### B.1. Recibir y registrar el reporte

**Actualmente:**

- El cliente reporta el problema por mensaje o llamada.
- No existe un registro formal de los problemas reportados.

**NT-6:** Sin un registro de los problemas que se han reportado, el equipo no puede identificar patrones — si el mismo módulo falla repetidamente, si un tipo de error aparece cada determinado tiempo, o si un cliente en particular tiene más incidentes que otros. SWEBOK v3 (Mantenimiento del Software) señala que el registro de defectos es una entrada necesaria para mejorar la calidad del sistema a lo largo del tiempo.

**Propuesta:**

- Todo reporte del cliente se registra en el Registro de errores reportados ([[01-Proyecto/06-Mantenimiento/Documentos_Apoyo/01-Registros/REG-06-02_Errores_Reportados|REG-06-02]]) antes de cualquier otra acción.
- El registro debe incluir:
    - Fecha y hora en que se recibió el reporte.
    - Nombre del cliente y del sistema.
    - Descripción del problema en las palabras del cliente.
    - Cómo se puede reproducir el problema, si el cliente lo sabe.
    - Quién recibió el reporte.

---

### B.2. Clasificar la prioridad del problema

**Actualmente:**

- El jefe de proyecto decide a criterio propio qué tan urgente es el problema.
- Solo se trata como urgente si el sistema está completamente caído o si hay un fallo muy grave.
- No existe un criterio escrito de qué hace que un problema sea urgente o no.

**NT-7:** La prioridad de un problema no debería depender de la percepción del momento. Un criterio definido protege al equipo de dos situaciones: tratar como urgente algo que no lo es (porque el cliente presiona), e ignorar algo que sí lo es (porque no se percibió como grave en el primer reporte). IEEE 1044-2009 (Estándar para la Clasificación de Anomalías del Software) proporciona un marco para clasificar defectos por severidad e impacto.

**Propuesta:**

Se clasifica el problema en una de tres categorías:

|Categoría|Descripción|Tiempo de atención|
|---|---|---|
|Crítico|El sistema está caído, inaccessible, o hay pérdida de datos.|El mismo día.|
|Alto|Una funcionalidad principal no funciona pero el sistema sigue operando.|[PENDIENTE: definir]|
|Normal|Un problema visual, un comportamiento inesperado menor, o una molestia.|[PENDIENTE: definir]|

- La categoría se registra junto con el reporte en el Registro de errores reportados.
- El tiempo de atención acordado con el cliente se basa en esta clasificación, no en la negociación del momento.

---

### B.3. Comunicar el tiempo de atención al cliente

**Actualmente:**

- Se discute con el cliente cuánto tiempo tomará el arreglo.
- La comunicación es verbal o por mensaje sin un registro del acuerdo.

**NT-8:** Acordar un tiempo de atención sin dejarlo por escrito puede generar conflicto si el equipo no lo resuelve en el plazo que el cliente creyó entender. Un mensaje simple que diga "vamos a revisar esto, te damos respuesta antes de las X horas" es suficiente para establecer una expectativa clara y dejar evidencia del compromiso.

**Propuesta:**

- Una vez clasificado el problema, se le comunica al cliente por escrito:
    - Que se recibió el reporte.
    - La categoría del problema según el criterio del equipo.
    - El tiempo estimado de atención.
- Esta comunicación se envía dentro de [PENDIENTE: definir tiempo máximo de respuesta inicial — sugerencia: 2 horas en horario laboral].

---

### B.4. Analizar y corregir el problema

**Actualmente:**

- El jefe de proyecto o el programador analiza el problema, lo resuelve, lo prueba manualmente y lo envía a producción.
- No queda registro de cuál era el problema, qué lo causaba, ni qué se hizo para corregirlo.

**NT-9:** Resolver un problema sin documentar la causa y la solución significa que si el mismo problema aparece en otro proyecto — o en el mismo sistema meses después — se vuelve a analizar desde cero. SWEBOK v3 (Mantenimiento del Software) señala que el conocimiento generado durante la corrección de defectos es un activo del equipo si se documenta, y se pierde si no se hace.

**Propuesta:**

- El programador asignado analiza el problema e identifica la causa raíz antes de hacer cambios en el código.
- Una vez identificada la causa, la registra en el Registro de errores reportados junto con la solución que se va a aplicar.
- Se implementa la corrección.
- Se verifica que la corrección resuelve el problema sin introducir nuevos errores en otras partes del sistema.

---

### B.5. Desplegar la corrección a producción

- La corrección se despliega siguiendo el Proceso de Despliegue de XookTech ([ver Proceso de Despliegue — XookTech]).
- Se prueban los flujos relacionados con el problema reportado antes de notificar al cliente.

---

### B.6. Notificar al cliente y cerrar el reporte

- Se notifica al cliente por escrito que el problema fue corregido y está disponible en producción.
- Se le pide que verifique que el comportamiento ahora es el esperado.
- Se registra en el Registro de errores reportados:
    - La causa raíz del problema.
    - La solución aplicada.
    - La fecha de cierre.
- Si el cliente confirma que está resuelto, el reporte se marca como cerrado.
- Si el problema persiste, se regresa al paso B.4.

---

## Justificación de Mejoras

**NT-1 — Registro formal de solicitudes**  
IEEE 12207:2017 (proceso de mantenimiento) establece que toda solicitud de modificación debe registrarse como condición previa a cualquier análisis o implementación. Sin registro, no hay trazabilidad: no se puede saber qué se pidió, cuándo, ni quién lo autorizó. En equipos pequeños, este registro puede ser tan sencillo como una hoja compartida con campos fijos.

**NT-2 y NT-3 — Cotización escrita y confirmación del cliente**  
SWEBOK v3 (Gestión de la Ingeniería del Software) señala que los acuerdos de trabajo deben estar documentados para que ambas partes tengan la misma referencia. La confirmación escrita del cliente antes de iniciar no es burocracia: es el mecanismo que evita trabajar sin autorización y cobrar sin acuerdo previo.

**NT-4 — Criterio para decidir cuándo diseñar**  
SWEBOK v3 (Mantenimiento del Software) distingue entre modificaciones menores que pueden implementarse directamente y cambios que requieren análisis de impacto antes de codificar. No tener ese criterio definido no significa que siempre se diseña: significa que a veces se diseña y a veces no, sin saber por qué, lo que hace el proceso impredecible.

**NT-5 — Cierre formal con el cliente**  
IEEE 12207:2017 incluye la confirmación del cliente como parte del cierre de cada solicitud de mantenimiento. Sin ese cierre, el límite entre lo que se entregó y lo que se pide después queda indefinido, generando conflictos sobre alcance y costos adicionales.

**NT-6 — Registro de errores reportados**  
SWEBOK v3 (Mantenimiento del Software) señala que el registro de defectos es una entrada necesaria para mejorar la calidad del sistema con el tiempo. Sin ese registro, cada problema se trata como un evento aislado y el equipo no puede identificar si hay módulos que fallan con frecuencia o causas recurrentes que podrían eliminarse de raíz.

**NT-7 — Clasificación de prioridad con criterios definidos**  
IEEE 1044-2009 (Estándar para la Clasificación de Anomalías del Software) proporciona un marco para evaluar defectos por severidad e impacto. Clasificar sin criterios hace que la prioridad dependa de la presión del cliente o del estado de ánimo del momento, no de la gravedad real del problema. Un criterio simple y escrito resuelve esto.

**NT-8 — Comunicación del tiempo de atención por escrito**  
Un acuerdo verbal sobre tiempos no es un acuerdo: es una interpretación de ambas partes que puede diferir. Comunicar el tiempo de atención por escrito establece una expectativa clara, reduce la ansiedad del cliente durante la espera, y protege al equipo si el tiempo acordado no se cumple por causas externas.

**NT-9 — Documentar causa raíz y solución**  
SWEBOK v3 (Mantenimiento del Software) trata el conocimiento generado durante la corrección de defectos como un activo del equipo. Documentar qué causó el problema y cómo se resolvió tiene dos beneficios directos: si el mismo problema aparece de nuevo, la corrección es inmediata; y si hay patrones de errores recurrentes, el equipo puede eliminar la causa desde el código en lugar de corregir síntomas repetidamente.

---

## Referencias

[1] SWEBOK v3.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2014. Capítulos consultados: Mantenimiento del Software, Gestión de la Ingeniería del Software, Calidad del Software.

[2] IEEE 12207:2017. _Ingeniería de Sistemas y Software — Procesos del Ciclo de Vida del Software_. IEEE/ISO. Procesos consultados: Mantenimiento, Verificación.

[3] IEEE 1044-2009. _Estándar para la Clasificación de Anomalías del Software_. IEEE.

[4] Registro de solicitudes de mantenimiento. _[por crear]_ — Documento interno para registrar todas las solicitudes de cambio o nuevas funcionalidades recibidas del cliente, con su estado y fecha de cierre.

[5] Registro de errores reportados. _[por crear]_ — Documento interno para registrar los problemas reportados por clientes, incluyendo causa raíz, solución aplicada y fecha de cierre.

[6] Plantilla de cotización de cambios. _[por crear]_ — Formato estandarizado para comunicar al cliente el alcance, costo y tiempo estimado de cualquier solicitud de mantenimiento antes de iniciar el trabajo.

[7] Lista de Verificación de Despliegue. _[por crear]_ — Ver Proceso de Despliegue de XookTech.

[8] Proceso de Codificación — XookTech. Documento del proceso de codificación del equipo.

[9] Proceso de Despliegue — XookTech. Documento del proceso de despliegue del equipo.
