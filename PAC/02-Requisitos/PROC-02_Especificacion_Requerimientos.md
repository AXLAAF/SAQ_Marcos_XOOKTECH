---
id: PROC-02
titulo: Proceso 02 - Especificacion de Requerimientos
version: "3.0"
estado: Activo
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-17
objetivo: Formalizar, verificar y validar cada requerimiento antes de incorporarlo a la linea base del proyecto.
alcance: Aplica a nuevas funcionalidades, ajustes al alcance original y cambios aprobados que deban convertirse en requerimientos trazables.
responsables:
  - Samuel Blanco (lider de negocio y validacion con cliente)
  - Axel Morales (analisis y especificacion tecnica)
disparador: Solicitud nueva, ajuste funcional o cambio aprobado que afecte el alcance del sistema.
criterio_entrada: Solicitud identificada en acta, minuta, acuerdo, correo o Change Request aprobado.
criterio_salida: Requerimiento verificado con checklist, validado por el cliente y trazado en la matriz correspondiente.
entradas:
  - Proyecto/01-Linea_Base/02-Propuesta_Recuperada.md
  - Proyecto/01-Linea_Base/03-Acuerdos_Cliente.md
  - Proyecto/01-Linea_Base/05-Minuta_Entrevista.md
  - Proyecto/07-Control/CR-XX_Nombre.md
salidas:
  - Proyecto/02-Requisitos/00-Pendientes/REQ-XXX_Nombre.md
  - Proyecto/02-Requisitos/01-Aprobados/REQ-XXX_Nombre.md
  - Proyecto/02-Requisitos/02-Rechazados/REQ-XXX_Nombre.md
  - Proyecto/02-Requisitos/Matriz_Trazabilidad.md
  - Evidencia de validacion del cliente
plantilla_artefacto: PAC/02-Requisitos/TEMPLATE-REQ.md
checklist_verificacion: PAC/02-Requisitos/CL-02_Verificacion_Requerimientos.md
notacion: "NT: indica una mejora aplicada al proceso actual."
---

# Proceso 02 - Especificacion de Requerimientos

## 1. Objetivo

Definir un flujo repetible para capturar, redactar, verificar y validar requerimientos del proyecto `Visualizador de Marcos`, de forma que cada `REQ` tenga alcance claro, criterios de aceptacion medibles, evidencia de aprobacion y trazabilidad con cambios, diseno y pruebas.

## 2. Alcance

- Aplica a requerimientos funcionales, no funcionales y reglas de negocio que deban documentarse en `Proyecto/02-Requisitos/`.
- Incluye solicitudes nuevas del cliente y requerimientos derivados de un `CR` aprobado.
- Cubre desde la captura inicial hasta la liberacion del requerimiento a la linea base documental.
- No autoriza implementacion tecnica si el requerimiento no esta verificado y validado.

## 3. Roles y Responsabilidades

| Rol | Responsable | Responsabilidad principal |
| :-- | :-- | :-- |
| Lider de negocio | Samuel Blanco | Recibir la solicitud, aclarar necesidad con el cliente, coordinar validacion y conservar evidencia de aprobacion. |
| Analista / desarrollo | Axel Morales | Redactar el requerimiento con la plantilla oficial, completar criterios de aceptacion, revisar trazabilidad y actualizar la matriz. |
| Cliente / solicitante | Enmarcame / representante | Aclarar la necesidad, validar el alcance propuesto y aprobar o rechazar por escrito. |

## 4. Entradas y Salidas

### Entradas

| Entrada | Uso en el proceso |
| :-- | :-- |
| `Proyecto/01-Linea_Base/02-Propuesta_Recuperada.md` | Contrastar la solicitud contra el alcance originalmente acordado. |
| `Proyecto/01-Linea_Base/03-Acuerdos_Cliente.md` | Confirmar condiciones de negocio y prioridades pactadas. |
| `Proyecto/01-Linea_Base/05-Minuta_Entrevista.md` | Recuperar lenguaje del cliente y decisiones funcionales. |
| `Proyecto/07-Control/CR-XX_Nombre.md` | Convertir cambios aprobados en requerimientos formales cuando aplique. |
| `PAC/02-Requisitos/TEMPLATE-REQ.md` | Estandarizar la estructura del artefacto REQ. |

### Salidas

| Salida | Resultado esperado |
| :-- | :-- |
| `Proyecto/02-Requisitos/00-Pendientes/REQ-XXX_Nombre.md` | Requerimiento capturado y en elaboracion. |
| `Proyecto/02-Requisitos/01-Aprobados/REQ-XXX_Nombre.md` | Requerimiento validado y liberado a la linea base. |
| `Proyecto/02-Requisitos/02-Rechazados/REQ-XXX_Nombre.md` | Requerimiento rechazado o descartado con causa documentada. |
| `Proyecto/02-Requisitos/Matriz_Trazabilidad.md` | Relacion actualizada entre fuente, REQ, diseno, pruebas y CR. |
| Evidencia de validacion | Correo, captura o minuta que respalde la aprobacion del cliente. |

## 5. Flujo ETVX

| Etapa | Entry | Task | Verification | Exit | Responsable |
| :-- | :-- | :-- | :-- | :-- | :-- |
| Captura | Solicitud identificada | Registrar el requerimiento con ID y fuente | Verificar que exista contexto minimo y ruta del archivo | `REQ` creado en `00-Pendientes` | Samuel |
| Especificacion | `REQ` creado | Redactar descripcion, reglas, flujos, BDD y trazabilidad | Revisar contra `TEMPLATE-REQ.md` | `REQ` completo para revision | Axel |
| Verificacion | `REQ` completo | Aplicar `CL-02_Verificacion_Requerimientos.md` | Medir cumplimiento, defectos y retrabajo | `REQ` verificado o devuelto a ajuste | Axel + Samuel |
| Validacion | `REQ` verificado | Presentar alcance y criterios al cliente | Confirmar aprobacion escrita | `REQ` aprobado o rechazado | Samuel + Cliente |
| Linea base | `REQ` aprobado | Mover archivo a `01-Aprobados` y actualizar matriz | Confirmar trazabilidad con CR y CP | Requerimiento en linea base | Axel |

## 6. Proceso Detallado

### Paso 1. Captura de la solicitud

**Actualmente:**
- El cliente comunica necesidades por WhatsApp, correo o llamada.
- Parte del contexto queda fuera del repositorio documental.

**NT-1:** Toda solicitud debe convertirse el mismo dia en un archivo `REQ-XXX_Nombre.md` en `Proyecto/02-Requisitos/00-Pendientes/`, aun cuando todavia falten detalles.

**Propuesta:**
- Samuel registra el requerimiento con ID consecutivo, titulo preliminar, fuente y solicitante.
- Se identifica si proviene del alcance original o de un `CR` aprobado.
- El estado inicial del artefacto es `Pendiente`.

### Paso 2. Especificacion del requerimiento

**Actualmente:**
- La redaccion puede quedar narrativa o incompleta.
- No siempre existen criterios de aceptacion medibles ni reglas de negocio cuantificadas.

**NT-2:** El uso de `PAC/02-Requisitos/TEMPLATE-REQ.md` es obligatorio para asegurar una estructura comun y eliminar ambiguedad entre negocio, desarrollo y pruebas.

**Propuesta:**
- Axel documenta descripcion general, objetivo de negocio, reglas de negocio, precondiciones, flujo principal, alternos, excepciones y criterios BDD.
- Se registran dependencias, casos de prueba esperados y `CR` asociados si el requerimiento nace de control de cambios.
- El estado del artefacto pasa a `Revisado` cuando la informacion minima de la plantilla esta completa.

### Paso 3. Verificacion interna del artefacto

**Actualmente:**
- La revision del requerimiento depende de experiencia individual.
- No existe un punto de control consistente antes de presentarlo al cliente.

**NT-3:** Antes de cualquier validacion externa, el requerimiento debe pasar el checklist `PAC/02-Requisitos/CL-02_Verificacion_Requerimientos.md` y corregirse si no alcanza el umbral definido.

**Propuesta:**
- Axel aplica una auto revision inicial usando la plantilla y corrige vacios obvios.
- Samuel ejecuta la verificacion formal con `CL-02` y registra porcentaje, defectos y observaciones en el mismo `REQ`.
- Si el resultado no cumple el umbral o falla un criterio critico, el `REQ` vuelve a ajuste y no pasa a cliente.

### Paso 4. Validacion con el cliente

**Actualmente:**
- El visto bueno suele quedar verbal o en mensajes dispersos.
- No siempre se conserva evidencia de aceptacion del alcance.

**NT-4:** Toda aprobacion debe quedar respaldada por correo, captura o minuta aceptada, vinculada en el campo `validacion_evidencia` del requerimiento.

**Propuesta:**
- Samuel presenta al cliente el alcance, criterios de aceptacion, restricciones y supuestos del `REQ`.
- El cliente aprueba o solicita ajustes por escrito.
- Si aprueba, el artefacto cambia a `Aprobado`; si no aprueba, regresa a especificacion o se mueve a `02-Rechazados` con causa documentada.

### Paso 5. Linea base y trazabilidad

**Actualmente:**
- La trazabilidad no siempre se actualiza al cierre.
- Los requisitos aprobados pueden coexistir con pendientes sin distincion operacional suficiente.

**NT-5:** La linea base documental se consolida solo con requerimientos aprobados, ubicados en `Proyecto/02-Requisitos/01-Aprobados/` y vinculados en la matriz de trazabilidad.

**Propuesta:**
- Axel mueve el archivo aprobado a `01-Aprobados`.
- Actualiza `Proyecto/02-Requisitos/Matriz_Trazabilidad.md` con fuente, diseno, casos de prueba y `CR` relacionados.
- Si el requerimiento genera trabajo posterior, se notifica a diseno, pruebas o control de cambios segun corresponda.

## 7. Verificacion y Validacion del Artefacto

### 7.1 Artefacto sujeto a control

- Artefacto: `REQ-XXX_Nombre.md`
- Plantilla obligatoria: `PAC/02-Requisitos/TEMPLATE-REQ.md`
- Checklist obligatorio: `PAC/02-Requisitos/CL-02_Verificacion_Requerimientos.md`

### 7.2 Criterios de calidad aplicables

| Criterio | Base | Aplicacion al REQ |
| :-- | :-- | :-- |
| Adecuacion funcional | ISO 25010 - Functional suitability | El requerimiento debe describir una necesidad real del negocio y el resultado esperado del sistema. |
| Correccion y consistencia | ISO 25010 / ISO 29148 | Las reglas, flujos y restricciones no deben contradecirse entre si ni con acuerdos previos. |
| Trazabilidad | SWEBOK / CMMI-CM | Cada `REQ` debe enlazar fuente, pruebas y `CR` cuando aplique. |
| Verificabilidad | ISO 25010 - Testability | Los criterios de aceptacion deben poder probarse de forma objetiva. |
| Comprensibilidad | ISO 25010 - Usability | La redaccion debe ser clara para negocio, desarrollo y pruebas. |
| Mantenibilidad documental | ISO 25010 - Maintainability | El artefacto debe permitir cambios controlados sin perder historial, impacto ni dependencias. |

### 7.3 Regla de verificacion

- Responsable: Samuel Blanco con apoyo tecnico de Axel Morales.
- Frecuencia: Cada vez que se crea o modifica un `REQ`, antes de validarlo con el cliente.
- Umbral de aceptacion: 90% de cumplimiento total y 100% de cumplimiento en items criticos del checklist.
- Evidencia: Resultado registrado en el campo de verificacion del `REQ` y observaciones en el checklist aplicado.

### 7.4 Regla de validacion

- Responsable: Samuel Blanco y cliente solicitante.
- Frecuencia: Una vez que el `REQ` pasa la verificacion interna.
- Umbral de aceptacion: Aprobacion explicita del cliente sobre alcance, restricciones y criterios de aceptacion.
- Evidencia: Correo, captura o minuta vinculada en `validacion_evidencia`.

### 7.5 Accion correctiva

- Si la verificacion falla, el `REQ` regresa al Paso 2 para retrabajo y no puede pasar a validacion.
- Si la validacion falla, Samuel documenta los ajustes solicitados y Axel actualiza el artefacto antes de una nueva revision.
- Si la solicitud deja de ser necesaria, el artefacto se mueve a `Proyecto/02-Requisitos/02-Rechazados/` con motivo documentado.

## 8. Metricas de seguimiento

- 100% de los `REQ` nuevos registrados con ID y fuente el mismo dia de la solicitud.
- 100% de los `REQ` aprobados con evidencia escrita de validacion.
- 100% de los `REQ` aprobados trazados con al menos un caso de prueba o una nota de no aplicacion.
- Tiempo objetivo de ciclo: maximo 5 dias habiles desde captura hasta aprobacion.

## 9. Trazabilidad y Documentos de Apoyo

1. `PAC/02-Requisitos/TEMPLATE-REQ.md`
2. `PAC/02-Requisitos/CL-02_Verificacion_Requerimientos.md`
3. `PAC/07-Control/PROC-03_Control_Cambios.md`
4. `Proyecto/02-Requisitos/Matriz_Trazabilidad.md`
5. `PAC/07-Control/PROC-06_Inspecciones.md` cuando el requerimiento requiera inspeccion formal.

## Historial de Cambios

| Version | Fecha | Autor | Descripcion |
| :-- | :-- | :-- | :-- |
| 1.0 | 2026-03-19 | Axel Morales | Creacion inicial del proceso. |
| 2.0 | 2026-05-13 | Adrian Zapata | Reestructuracion ETVX y mejoras SQA iniciales. |
| 3.0 | 2026-05-17 | OpenCode | Refactor para separar PAC/Proyecto e incorporar verificacion, validacion y checklist completo. |
