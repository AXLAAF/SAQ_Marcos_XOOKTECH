---
name: proceso-mejora
description: >
  Usa este skill para redactar documentos formales de proceso con secciones de mejora continua,
  al estilo de documentos de Aseguramiento de Calidad de Software (SQA). Aplica cuando el usuario
  quiera documentar cómo funciona un proceso actualmente, proponer mejoras con notación NT:,
  justificar los cambios, y referenciar documentos de apoyo (checklists, guías, formatos).
  Úsalo siempre que el usuario diga: "documenta este proceso", "genera un proceso", "crea un
  documento de proceso", "quiero proponer una mejora al proceso", o cuando entregue una descripción
  de cómo se hace algo hoy y cómo quiere que se haga mañana. El output es un documento estructurado
  en español, con pasos numerados, lenguaje claro, y secciones "Actualmente / Propuesta" marcadas con NT:.
---

# Skill: Redacción de Documentos de Proceso con Mejoras (NT:)

## ¿Para qué sirve este skill?

Para producir documentos de proceso formales que:
- Describen el proceso **tal como está hoy** (sección "Actualmente")
- Proponen mejoras usando la notación **NT:** (Nota Técnica) de manera inline
- Presentan el proceso **mejorado** (sección "Propuesta")
- Justifican cada mejora con argumentos claros
- Referencian documentos externos cuando aplica (checklists, guías, formatos)

---

## Entradas que debes pedir al usuario

Antes de generar, asegúrate de tener:

1. **Área y nombre del proceso** — ¿Qué área es? ¿Cómo se llama el proceso?
2. **Responsables** — ¿Quién lleva a cabo el proceso?
3. **Entradas del proceso** — ¿Qué se necesita para que el proceso arranque?
4. **Salidas esperadas** — ¿Qué produce el proceso al terminar?
5. **Proceso actual** — Cómo se hace hoy, paso a paso (puede ser informal, el skill lo estructura)
6. **Qué quiere mejorar** — Puede ser un problema detectado, un dolor, una ineficiencia, o una meta
7. **Documentos de apoyo existentes** — Checklists, guías, formatos que ya existen y pueden referenciarse
8. **¿Quiere justificación?** — Si desea que cada NT: lleve su argumento explicado al final

Si el usuario no da todos estos datos, infiere lo razonable y señala los supuestos que estás haciendo.

---

## Estructura del documento a generar

### Encabezado

```
Área de proceso: [Nombre del área]
Nombre Proceso: [Nombre descriptivo del proceso]
Responsable: [Quién lo ejecuta]
Entradas: [Qué inicia el proceso]
Salidas: [Qué produce el proceso]
Notación: NT: indica una Nota Técnica con sugerencia de mejora al proceso.
```

---

### Información Preliminar (si aplica)

Incluye una tabla con los documentos que se necesitan en el proceso, con su ruta o ubicación:

```
| Nombre del Documento      | Ubicación / Ruta                        |
|---------------------------|-----------------------------------------|
| [Nombre del doc]          | [Carpeta o sistema donde se encuentra]  |
```

Si el usuario no maneja rutas formales, omite la columna de ruta o usa una descripción simple.

---

### Proceso

Los pasos se numeran. Cada paso puede tener sub-bullets con detalles.

**Regla para las secciones "Actualmente / Propuesta":**

Cuando un paso tiene una forma actual que se quiere mejorar, se estructura así:

```
N. [Nombre del paso]

  Actualmente:
  - Paso tal como se hace hoy.
  - Paso tal como se hace hoy.

  NT: [Descripción breve de la mejora propuesta. Qué cambia y por qué conviene.]

  Propuesta:
  - Paso mejorado.
  - Paso mejorado.
```

**Regla para mejoras menores inline (dentro de un paso):**

```
- El responsable revisa el diseño. NT: Se recomienda registrar las observaciones en un Reporte de Junta
  ([ver formato](ruta/al/documento.docx)) para dejar trazabilidad de las decisiones tomadas.
```

**Cuándo usar NT: inline vs. sección completa Actualmente/Propuesta:**
- Usa la **sección completa** cuando el cambio afecta el flujo general del paso o reemplaza varios sub-pasos.
- Usa **NT: inline** cuando es una sugerencia puntual que complementa un paso que ya es correcto en esencia.

---

### Referencias a otros documentos

Cuando en un paso se menciona un documento de apoyo, refiérelo así:

- En el cuerpo del texto: `([ver nombre del documento](ruta/o/descripción))`
- Si el usuario no tiene ruta, usa: `([ver Guía de X])`
- Si el documento aún no existe pero se propone crearlo: `([ver Formato sugerido: Nombre del Formato])`

Al final del documento, incluye una sección de **Referencias** en formato numerado:

```
[1] Título del libro o fuente. Autor. Editorial, año.
[2] Nombre del documento interno. Descripción breve.
```

---

### Sección de Justificación (si el usuario la solicita)

Al final del proceso, antes de las referencias, agrega una sección:

```
## Justificación de Mejoras

NT-1: [Repite el texto del primer NT] 
Justificación: [Argumento claro. ¿Qué problema resuelve? ¿Qué beneficio trae? 
¿Hay una práctica estándar, herramienta, o experiencia que lo respalde?]

NT-2: ...
```

Numera los NT: en el cuerpo del documento (NT-1:, NT-2:, etc.) para que correspondan con esta sección.

---

## Reglas de escritura

- **Lenguaje simple y directo.** Evita tecnicismos innecesarios. Si un término técnico es necesario, explícalo brevemente la primera vez.
- **Pasos concisos.** Cada bullet es una sola acción. Si un paso tiene más de 3 líneas, probablemente debe dividirse.
- **Voz activa.** "El líder del proyecto crea el repositorio" en lugar de "El repositorio es creado por el líder del proyecto."
- **Sin ambigüedad.** Cada paso debe decir *quién* hace *qué* y *cuándo*.
- **Las NT: no son críticas al proceso actual** — son oportunidades. El tono es constructivo, no correctivo.

---

## Ejemplo mínimo de output

```
Área de proceso: Ventas
Nombre Proceso: Seguimiento a prospectos.
Responsable: Ejecutivo de cuenta.
Entradas: Lista de prospectos contactados.
Salidas: Registro de seguimiento actualizado.
Notación: NT: indica una Nota Técnica con sugerencia de mejora al proceso.

Proceso.

1. Registro del prospecto.

   Actualmente:
   - El ejecutivo anota los datos del prospecto en una libreta o en su correo.
   - No existe un formato común entre el equipo.

   NT-1: Se sugiere utilizar un CRM o al menos una hoja compartida con campos fijos
   (nombre, empresa, canal de contacto, fecha, estatus) para que el equipo tenga
   visibilidad común y no se pierda información cuando alguien falta.

   Propuesta:
   - El ejecutivo registra al prospecto en el CRM del equipo ([ver Guía de uso del CRM])
     llenando los campos: nombre, empresa, canal de contacto, fecha y estatus inicial.
   - Si no hay acceso al CRM, usa la Hoja de Seguimiento compartida ([ver Formato: Hoja de Seguimiento]).

2. Primer contacto.
   - El ejecutivo se comunica con el prospecto por el canal preferido (WhatsApp, correo o teléfono).
   - Registra el resultado del contacto en el CRM: respondió / no respondió / agendó reunión.
   NT-2: Se recomienda definir un tiempo máximo de 48 horas para el primer contacto después
   de que el prospecto entra a la lista, para evitar que el interés se enfríe.

## Justificación de Mejoras

NT-1: Uso de CRM o hoja compartida para registro de prospectos.
Justificación: Cuando cada ejecutivo guarda la información de manera distinta,
se pierde contexto si la persona falta, rota, o el prospecto escala a otro nivel.
Un registro común también permite identificar patrones (qué canal convierte mejor,
en qué etapa se caen los prospectos).

NT-2: Tiempo máximo de 48 horas para primer contacto.
Justificación: Los estudios de seguimiento en ventas B2B muestran que la probabilidad
de conversación cae significativamente después de las primeras 24-48 horas del primer
interés. Definir este límite como parte del proceso establece un estándar medible.

Referencias
[1] Formato sugerido: Hoja de Seguimiento. Documento interno propuesto para estandarizar
    el registro de prospectos cuando no se cuenta con CRM.
[2] Guía de uso del CRM. Documento de onboarding del sistema de gestión de clientes.
```

---

## Notas para el modelo que usa este skill

- Si el usuario entrega el proceso de forma desordenada o verbal, **estructúralo tú** — no le pidas que lo reescriba.
- Si el usuario no sabe qué mejorar, **propón tú las NT:** basándote en lo que describes como proceso actual. Identifica: pasos sin trazabilidad, comunicación verbal sin respaldo, falta de formatos, cuellos de botella obvios.
- Si el proceso tiene variantes por tecnología, área o perfil (como PHP vs Ruby), genera secciones separadas dentro del mismo documento o documentos distintos según lo pida el usuario.
- Las referencias a documentos que **no existen aún** deben estar marcadas claramente como "Formato sugerido:" o "Guía propuesta:" para que el lector sepa que es algo por crear.
- No generes referencias bibliográficas a libros externos a menos que el usuario lo pida explícitamente o el contexto lo justifique.
