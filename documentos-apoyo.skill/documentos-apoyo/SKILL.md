---
ºname: documentos-apoyo
description: >
  Usa este skill para generar documentos de apoyo formales en Markdown: registros,
  listas de verificación, plantillas de comunicación, formatos de cotización, formatos
  de solicitud, formatos de entrevista y cualquier otro formato de apoyo a un proceso.
  Aplica cuando el usuario pida: "genera el formato de X", "crea el registro de Y",
  "necesito una lista de verificación para Z", "dame la plantilla para comunicarle al
  cliente que...", "crea el formato de cotización", o cuando un proceso existente
  referencie un documento [por crear]. El output es siempre un archivo Markdown listo
  para usarse, con instrucciones breves por campo para que cualquier integrante del
  equipo lo llene correctamente sin preguntar. Los documentos se conectan con los
  procesos existentes cuando aplica.
---

# Skill: Generación de Documentos de Apoyo

## ¿Para qué sirve este skill?

Para generar documentos de apoyo formales que acompañan los procesos del equipo:

- **Registros** — Listas donde se anota lo que va ocurriendo (errores, solicitudes, entregas, servidores).
- **Listas de verificación** — Checklists que alguien marca paso a paso antes de hacer algo crítico.
- **Plantillas de comunicación** — Mensajes o correos con estructura fija para comunicarse con el cliente.
- **Formatos de cotización o acuerdo** — Documentos para formalizar el alcance, costo y tiempo con el cliente.
- **Formatos de solicitud o petición** — Formularios para pedir algo de forma estructurada (acceso, recurso, cambio).
- **Formatos de entrevista o levantamiento** — Guías de preguntas para recopilar información de clientes o usuarios.

---

## Entradas que debes pedir al usuario

Antes de generar, asegúrate de tener:

1. **Qué documento se necesita** — Nombre y tipo (registro, lista de verificación, plantilla, formato, etc.).
2. **Para qué proceso sirve** — ¿A qué proceso pertenece o qué actividad apoya? ¿Referencia algún proceso existente?
3. **Quién lo llena** — Puede ser el jefe de proyecto, el programador, el cliente, o cualquier miembro del equipo.
4. **Qué información necesita capturar** — Qué datos deben quedar registrados cuando alguien lo use.
5. **Hay campos que el usuario ya sabe que quiere incluir** — Si mencionó campos específicos, inclúyelos todos.

Si el usuario no da todos estos datos, usa el contexto del proceso al que pertenece el documento para inferir lo necesario. Señala los supuestos que estás haciendo al inicio del documento generado.

---

## Reglas generales de todos los documentos

- **Lenguaje simple.** Sin tecnicismos. Si un término es necesario, explícalo en la instrucción del campo.
- **Instrucción breve por campo.** Cada campo lleva entre paréntesis o en cursiva una instrucción de una línea que explica qué escribir ahí. El objetivo es que cualquier integrante del equipo lo llene bien sin preguntar a nadie.
- **Sin redundancia.** Si el nombre del campo ya es suficientemente claro, la instrucción puede omitirse.
- **Los campos obligatorios se marcan con asterisco (\*).** Los opcionales no llevan marcador.
- **Referencia al proceso de origen cuando aplica.** Si el documento apoya un proceso existente, se menciona al inicio.

---

## Estructura según tipo de documento

---

### Tipo 1 — Registro

Un registro es un documento donde se va anotando lo que ocurre con el tiempo. Funciona como una bitácora o tabla acumulativa.

**Encabezado del documento:**

```markdown
# [Nombre del Registro] — XookTech

**Proceso relacionado:** [Nombre del proceso al que pertenece, o "General" si aplica a varios]
**Responsable de mantenerlo:** [Quién lo actualiza]
**Instrucciones generales:** [Una o dos líneas de cuándo se usa este registro y quién lo llena]
```

**Tabla de campos:**

Cada columna es un campo. Incluye su instrucción en el encabezado entre paréntesis.

```markdown
| Campo 1 * (instrucción) | Campo 2 * (instrucción) | Campo 3 (instrucción) |
|-------------------------|-------------------------|-----------------------|
|                         |                         |                       |
```

**Sección de notas al pie (si aplica):**

```markdown
## Notas

- [Cualquier aclaración sobre cómo usar el registro, casos especiales, o cómo archivar cuando se llena.]
```

---

### Tipo 2 — Lista de Verificación

Una lista de verificación es un documento que alguien recorre punto por punto antes de hacer algo crítico — un despliegue, una entrega, un cierre de proyecto.

**Encabezado del documento:**

```markdown
# [Nombre de la Lista de Verificación] — XookTech

**Proceso relacionado:** [Nombre del proceso]
**Cuándo se usa:** [En qué momento del proceso se completa esta lista]
**Quién la completa:** [Rol responsable]
**Instrucciones:** Marca cada punto con [x] cuando esté cumplido. No avances al siguiente paso del proceso hasta que todos los puntos marcados como obligatorios (*) estén completos.
```

**Secciones de verificación:**

Agrupa los puntos por tema cuando el proceso tiene varias etapas. Cada punto es una afirmación verificable, no una pregunta.

```markdown
## [Nombre de la sección]

- [ ] * [Afirmación verificable. Instrucción breve de cómo verificarla si no es obvia.]
- [ ] * [Afirmación verificable.]
- [ ]   [Afirmación opcional — recomendada pero no bloqueante.]
```

**Al final de la lista:**

```markdown
---

**Completado por:** ________________________________  
**Fecha:** ________________________________  
**Observaciones:** ________________________________
```

---

### Tipo 3 — Plantilla de Comunicación

Una plantilla de comunicación es un mensaje con estructura fija para enviarle al cliente en situaciones recurrentes: confirmar una solicitud, notificar una entrega, dar seguimiento a un reporte, etc.

**Encabezado del documento:**

```markdown
# Plantilla: [Nombre de la situación] — XookTech

**Cuándo se usa:** [Descripción de la situación que dispara el envío de este mensaje]
**Canal:** [Mensaje directo / Correo / El que use el proyecto]
**Quién lo envía:** [Rol]
**Instrucciones:** Reemplaza los campos entre corchetes [ ] con la información del caso. Elimina las líneas de instrucción antes de enviar.
```

**Cuerpo del mensaje:**

```markdown
---

Hola [Nombre del cliente],

[Párrafo de apertura según el contexto — confirmación, notificación, seguimiento.]

[Párrafo con los detalles específicos del caso: qué se acordó, qué se entregó, qué se detectó, etc.]

[Párrafo de cierre: qué se espera del cliente, cuál es el siguiente paso, o cómo puede contactar al equipo.]

Quedo al pendiente.  
[Nombre de quien envía]  
XookTech

---
```

**Nota de uso:**

```markdown
> Esta plantilla es un punto de partida. Puede ajustarse al tono de la relación con el cliente específico, siempre que conserve la información esencial marcada con *.
```

---

### Tipo 4 — Formato de Cotización o Acuerdo

Un formato de cotización documenta lo que se acordó con el cliente antes de iniciar un trabajo: qué se hace, cuánto cuesta, en cuánto tiempo.

**Encabezado del documento:**

```markdown
# Cotización de [Tipo de trabajo: Cambio / Nueva funcionalidad / Corrección] — XookTech

**Folio:** * (Número consecutivo para identificar esta cotización. Ejemplo: COT-2025-001)
**Fecha:** * (Fecha en que se emite esta cotización)
**Cliente:** * (Nombre del cliente o empresa)
**Sistema:** * (Nombre del sistema al que aplica el trabajo)
**Elaboró:** * (Nombre del jefe de proyecto que la genera)
```

**Secciones:**

```markdown
## Solicitud recibida

(Describe en una o dos líneas qué pidió el cliente, usando sus propias palabras o un resumen fiel de la solicitud registrada.)

## Alcance del trabajo

(Describe qué se va a hacer. Sé específico: qué módulos se tocan, qué funcionalidades cambian, qué queda fuera de esta cotización.)

| Concepto                     | Descripción breve                        |
|------------------------------|------------------------------------------|
| [Nombre de la actividad]     | [Qué incluye]                            |

## Lo que no incluye esta cotización

(Lista lo que explícitamente NO se va a hacer con este trabajo. Esto evita malentendidos sobre el alcance.)

- [Elemento fuera de alcance]

## Costo y forma de pago

| Concepto         | Monto         |
|------------------|---------------|
| [Descripción]    | $[Cantidad]   |
| **Total**        | **$[Total]**  |

**Forma de pago:** (Describe cómo y cuándo se paga — anticipo, contra entrega, mensual, etc.)

## Tiempo estimado

**Inicio estimado:** (Cuándo se puede comenzar, dado que el cliente apruebe esta cotización)  
**Entrega estimada:** (Fecha o número de días hábiles desde la aprobación)

## Condiciones

(Lista las condiciones que aplican a esta cotización. Ejemplos: tiempo de validez, qué pasa si el alcance cambia, tiempos de respuesta esperados del cliente para revisiones.)

## Aprobación del cliente

Al responder a este documento con un "de acuerdo", "aprobado" o equivalente, el cliente confirma que revisó y aceptó el alcance, costo y tiempo descritos.

**Aprobado por:** ________________________________  
**Fecha de aprobación:** ________________________________
```

---

### Tipo 5 — Formato de Solicitud o Petición

Un formato de solicitud es un documento que alguien llena para pedir algo de forma estructurada: acceso a un sistema, un recurso, un cambio, etc.

**Encabezado del documento:**

```markdown
# Solicitud de [Nombre de lo que se pide] — XookTech

**Folio:** * (Número consecutivo para identificar la solicitud)
**Fecha:** * (Fecha en que se hace la solicitud)
**Solicitante:** * (Nombre de quien pide)
**Área o proyecto:** * (A qué proyecto o área está relacionada esta solicitud)
**Dirigida a:** * (Quién debe atender o aprobar esta solicitud)
```

**Secciones:**

```markdown
## Descripción de la solicitud

(Describe qué se está pidiendo. Sé específico: qué se necesita, para qué proyecto, y para cuándo.)

## Justificación

(Explica por qué se necesita. Una o dos líneas es suficiente.)

## Urgencia

- [ ] Normal — puede atenderse en el flujo regular de trabajo.
- [ ] Alta — se necesita antes de [fecha] porque [razón].
- [ ] Crítica — bloquea el avance del proyecto si no se atiende hoy.

## Información adicional

(Cualquier detalle que ayude a quien va a atender la solicitud — versiones, accesos necesarios, contexto del proyecto.)

---

**Atendida por:** ________________________________  
**Fecha de atención:** ________________________________  
**Resultado:** ________________________________
```

---

### Tipo 6 — Formato de Entrevista o Levantamiento de Información

Un formato de entrevista es una guía de preguntas para recopilar información del cliente o del usuario antes de diseñar o desarrollar algo.

**Encabezado del documento:**

```markdown
# Formato de Levantamiento: [Nombre del proyecto o módulo] — XookTech

**Fecha:** * (Fecha de la sesión)
**Cliente o usuario entrevistado:** * (Nombre y rol de quien responde)
**Conduce la entrevista:** * (Nombre del jefe de proyecto o quien levanta la información)
**Objetivo:** (En una línea, qué información se busca obtener con esta entrevista)
```

**Secciones de preguntas:**

Agrupa las preguntas por tema. Deja espacio debajo de cada pregunta para anotar la respuesta.

```markdown
## [Tema 1 — ejemplo: Contexto del negocio]

1. [Pregunta abierta sobre el tema.]  
   **Respuesta:**

2. [Pregunta específica.]  
   **Respuesta:**

## [Tema 2 — ejemplo: Proceso actual]

3. [Pregunta sobre cómo se hace algo hoy.]  
   **Respuesta:**
```

**Al final:**

```markdown
---

## Acuerdos y siguientes pasos

(Anota aquí lo que se acordó durante la sesión y qué sigue — quién hace qué y para cuándo.)

| Acuerdo o acción             | Responsable       | Fecha límite |
|------------------------------|-------------------|--------------|
|                              |                   |              |

**Firma o confirmación del cliente:** ________________________________
```

---

## Notas para el modelo que usa este skill

- Si el usuario pide un documento que está marcado como `[por crear]` en un proceso existente, genera el documento que corresponde al nombre exacto con el que fue referenciado en el proceso.
- Si el usuario no especifica el tipo de documento, infiere el tipo a partir del nombre y el contexto. Ejemplo: "Registro de errores reportados" → Tipo 1 (Registro). "Lista de Verificación de Despliegue" → Tipo 2.
- Si el documento va a ser llenado por "cualquier miembro del equipo", las instrucciones de cada campo deben ser suficientemente claras para alguien que no conoce el proceso de memoria. Sé más explícito en las instrucciones, no menos.
- Si el proceso de origen tiene NT: con información sobre qué debe contener el documento, extrae esa información e inclúyela como campos o criterios dentro del documento.
- El folio o número consecutivo es obligatorio en registros y cotizaciones. Si el usuario no mencionó un sistema de folios, propón uno simple: `[SIGLAS]-[AÑO]-[NÚMERO]`. Ejemplo: `REG-ERR-2025-001`.
- Los documentos en Markdown deben ser funcionales tal como están — no requieren que el usuario los reescriba. Los campos vacíos se representan con líneas o paréntesis con la instrucción.
- Cuando el documento referencia un proceso existente, incluye el nombre del proceso en el encabezado tal como aparece en los documentos del equipo.
