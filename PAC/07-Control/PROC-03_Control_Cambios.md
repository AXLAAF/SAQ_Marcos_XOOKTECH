---
id: PROC-03
titulo: Proceso 03 - Control de Cambios
version: "2.0"
estado: Activo
tipo: Proceso
fecha_creacion: 2026-05-14
ultima_revision: 2026-05-17
objetivo: Registrar, analizar, verificar, validar y cerrar cambios al alcance con trazabilidad documental y tecnica.
alcance: Aplica a toda solicitud que modifique requerimientos, costo, tiempo, calidad, pruebas o linea base del proyecto.
responsables:
  - Samuel Blanco (registro, seguimiento y validacion comercial)
  - Axel Morales (analisis tecnico e impacto)
disparador: Solicitud de cambio del cliente, ajuste interno o hallazgo que altere el alcance vigente.
criterio_entrada: Cambio identificado y registrado con datos minimos de origen, descripcion y artefactos afectados.
criterio_salida: `CR` con decision documentada, checklist aprobado y artefactos actualizados cuando el cambio es autorizado.
entradas:
  - Proyecto/01-Linea_Base/03-Acuerdos_Cliente.md
  - Proyecto/02-Requisitos/Matriz_Trazabilidad.md
  - Proyecto/02-Requisitos/01-Aprobados/REQ-XXX_Nombre.md
  - PAC/07-Control/TEMPLATE-CR.md
salidas:
  - Proyecto/07-Control/CR-XX_Nombre.md
  - Proyecto/02-Requisitos/Matriz_Trazabilidad.md
  - Proyecto/02-Requisitos/REQ-XXX_Nombre.md
  - Evidencia de aprobacion o rechazo del cambio
  - Casos de prueba nuevos o actualizados
plantilla_artefacto: PAC/07-Control/TEMPLATE-CR.md
checklist_verificacion: PAC/07-Control/CL-03_Verificacion_Cambios.md
notacion: "NT: indica una mejora aplicada al proceso actual."
---

# Proceso 03 - Control de Cambios

## 1. Objetivo

Formalizar todo cambio al alcance del proyecto `Visualizador de Marcos` para que ninguna funcionalidad, corrección o ajuste sea implementado sin registro, análisis de impacto, verificación documental, validación por el cliente y actualización de la linea base.

## 2. Alcance

- Aplica a cambios funcionales, correcciones de alcance, extras comerciales, retrabajos relevantes y decisiones de no implementar.
- Cubre el ciclo completo desde la solicitud hasta el cierre documental del `CR`.
- Incluye la actualización de requerimientos, matriz de trazabilidad y casos de prueba cuando el cambio se aprueba.
- No sustituye el proceso de desarrollo ni el de requisitos; los activa o actualiza según el impacto aprobado.

## 3. Roles y Responsabilidades

| Rol | Responsable | Responsabilidad principal |
| :-- | :-- | :-- |
| Lider de negocio | Samuel Blanco | Registrar el cambio, consolidar contexto, negociar con el cliente y resguardar evidencia de decision. |
| Analista tecnico | Axel Morales | Determinar impacto en alcance, tiempo, costo, calidad, pruebas y artefactos. |
| Cliente / aprobador | Enmarcame / representante | Aprobar o rechazar el cambio con base en impacto, prioridad y costo. |

## 4. Entradas y Salidas

### Entradas

| Entrada | Uso en el proceso |
| :-- | :-- |
| `Proyecto/01-Linea_Base/03-Acuerdos_Cliente.md` | Distinguir alcance original de extras o ajustes posteriores. |
| `Proyecto/02-Requisitos/01-Aprobados/REQ-XXX_Nombre.md` | Identificar comportamiento actual y criterios afectados. |
| `Proyecto/02-Requisitos/Matriz_Trazabilidad.md` | Medir impacto en diseno, pruebas y dependencias. |
| `PAC/07-Control/TEMPLATE-CR.md` | Registrar el cambio con estructura uniforme. |

### Salidas

| Salida | Resultado esperado |
| :-- | :-- |
| `Proyecto/07-Control/CR-XX_Nombre.md` | Solicitud de cambio analizada, verificada y con decision formal. |
| `Proyecto/02-Requisitos/REQ-XXX_Nombre.md` | Requerimiento actualizado cuando el cambio es aprobado. |
| `Proyecto/02-Requisitos/Matriz_Trazabilidad.md` | Relacion actualizada entre `CR`, `REQ` y `CP`. |
| Evidencia de aprobacion o rechazo | Respaldo comercial y tecnico de la decision. |
| Casos de prueba actualizados | Evidencia de impacto en validacion del sistema. |

## 5. Flujo ETVX

| Etapa | Entry | Task | Verification | Exit | Responsable |
| :-- | :-- | :-- | :-- | :-- | :-- |
| Registro | Cambio detectado | Crear `CR-XX_Nombre.md` con origen, descripcion y prioridad | Revisar que exista informacion minima | `CR` en `Pendiente` | Samuel |
| Analisis | `CR` registrado | Estimar impacto en alcance, tiempo, costo, calidad y pruebas | Confirmar impacto completo y artefactos afectados | `CR` en `En_Analisis` con impacto documentado | Axel |
| Verificacion | Analisis completo | Aplicar `CL-03_Verificacion_Cambios.md` | Medir cumplimiento y defectos del artefacto `CR` | `CR` verificado o devuelto a ajuste | Samuel + Axel |
| Validacion | `CR` verificado | Presentar decision propuesta al cliente | Confirmar aprobacion o rechazo por escrito | `CR` en `Aprobado` o `Rechazado` | Samuel + Cliente |
| Cierre | Cambio aprobado o rechazado | Actualizar `REQ`, matriz, pruebas y estado final | Confirmar trazabilidad documental y tecnica | `CR` `Implementado` o `Cerrado` | Samuel + Axel |

## 6. Proceso Detallado

### Paso 1. Registro del cambio

**Actualmente:**
- La solicitud puede quedarse en conversaciones de WhatsApp, llamada o contexto operativo.
- No siempre existe un identificador formal antes de hablar de fechas o costos.

**NT-1:** Toda solicitud debe convertirse el mismo dia en un `CR-XX_Nombre.md` dentro de `Proyecto/07-Control/` usando `PAC/07-Control/TEMPLATE-CR.md`.

**Propuesta:**
- Samuel asigna ID consecutivo, estado `Pendiente`, origen, solicitante y descripcion resumida.
- Se identifica el `REQ` afectado o se declara que aun no existe uno y debera generarse si el cambio es aprobado.

### Paso 2. Analisis de impacto

**Actualmente:**
- El esfuerzo puede estimarse de manera rapida o intuitiva.
- No siempre se documenta el efecto sobre pruebas, calidad o acuerdos previos.

**NT-2:** Ningun cambio puede prometerse al cliente sin analisis explicito de impacto en alcance, tiempo, costo, calidad y artefactos afectados.

**Propuesta:**
- Axel revisa el cambio contra acuerdos base, requerimientos y matriz de trazabilidad.
- Documenta impacto en `REQ`, diseno, pruebas, costo y riesgo tecnico.
- Se listan casos de prueba a crear o actualizar y si existe necesidad de nuevo requerimiento.

### Paso 3. Verificacion documental del CR

**Actualmente:**
- Puede existir un `CR`, pero sin un control uniforme de completitud antes de presentarlo.
- Falta un punto de calidad que evite decisiones sobre informacion incompleta.

**NT-3:** Todo `CR` debe pasar `PAC/07-Control/CL-03_Verificacion_Cambios.md` antes de solicitar aprobacion del cliente.

**Propuesta:**
- Samuel revisa que el registro comercial y la evidencia de origen sean suficientes.
- Axel revisa que el analisis tecnico, la trazabilidad y el impacto de pruebas sean completos.
- Si el `CR` no cumple el umbral o falla un item critico, regresa a `En_Analisis` hasta corregirse.

### Paso 4. Validacion y decision del cliente

**Actualmente:**
- La aprobacion puede quedar verbal o implicita.
- Los cambios extra se mezclan con el alcance original y generan conflicto posterior.

**NT-4:** Toda decision debe quedar por escrito y ligada al `CR` mediante correo, captura o minuta aceptada.

**Propuesta:**
- Samuel presenta alcance, impacto, costo, tiempo y riesgo al cliente.
- El cliente aprueba, rechaza o solicita ajuste por escrito.
- El `CR` registra `decision`, `aprobado_por`, `fecha_aprobacion` y `evidencia_aprobacion`.

### Paso 5. Ejecucion controlada del cambio

**Actualmente:**
- El equipo puede empezar a resolver el cambio apenas lo entiende tecnicamente.
- La implementacion puede adelantarse a la decision formal.

**NT-5:** Solo los `CR` aprobados pueden pasar a implementacion y toda evidencia tecnica debe usar el mismo ID del cambio.

**Propuesta:**
- Axel actualiza o crea el `REQ` correspondiente mediante `PROC-02`.
- Se actualizan pruebas y trazabilidad antes o durante la implementacion planificada.
- Si el cambio es rechazado, no se implementa y el `CR` se cierra con causa documentada.

### Paso 6. Cierre y actualizacion de linea base

**Actualmente:**
- El `CR` puede existir sin reflejarse completamente en requerimientos, pruebas o matriz.
- La decision final no siempre queda visible para auditoria.

**NT-6:** El cierre del `CR` exige coherencia entre decision, `REQ`, matriz de trazabilidad, pruebas y evidencia final.

**Propuesta:**
- Samuel y Axel verifican que el `CR` tenga decision final y evidencia asociada.
- Se actualizan `REQ`, `CP` y `Proyecto/02-Requisitos/Matriz_Trazabilidad.md`.
- El estado final del cambio se deja como `Implementado`, `Rechazado` o `Cerrado`, segun corresponda.

## 7. Verificacion y Validacion del Artefacto

### 7.1 Artefacto sujeto a control

- Artefacto: `CR-XX_Nombre.md`
- Plantilla obligatoria: `PAC/07-Control/TEMPLATE-CR.md`
- Checklist obligatorio: `PAC/07-Control/CL-03_Verificacion_Cambios.md`

### 7.2 Criterios de calidad aplicables

| Criterio | Base | Aplicacion al CR |
| :-- | :-- | :-- |
| Adecuacion funcional | ISO 25010 - Functional suitability | El cambio debe describir claramente la necesidad y el resultado esperado. |
| Correccion del impacto | ISO 25010 / analisis de impacto | El esfuerzo, costo, riesgos y artefactos afectados deben ser coherentes con el cambio descrito. |
| Trazabilidad | CMMI-CM / SWEBOK | El `CR` debe enlazar origen, `REQ`, pruebas y evidencia de decision. |
| Auditabilidad | SCM / SQA | La decision debe poder justificarse con datos y evidencia documental. |
| Testabilidad | ISO 25010 - Testability | El impacto debe identificar pruebas nuevas, actualizadas o no aplicables. |
| Control de configuracion | CMMI-CM | Ningun cambio aprobado debe quedar fuera de la linea base documental. |

### 7.3 Regla de verificacion

- Responsable: Samuel Blanco y Axel Morales.
- Frecuencia: Dos veces por cambio, antes de aprobarlo y antes de cerrarlo.
- Umbral de aceptacion: 90% de cumplimiento total y 100% en items criticos del checklist.
- Evidencia: Resultado de `CL-03` y registro de verificacion dentro del `CR`.

### 7.4 Regla de validacion

- Responsable: Samuel Blanco y cliente aprobador.
- Frecuencia: Una vez concluido el analisis de impacto y antes de programar implementacion.
- Umbral de aceptacion: Aprobacion o rechazo explicito del cliente con fecha y medio de evidencia.
- Evidencia: `evidencia_aprobacion` vinculada en el `CR`.

### 7.5 Accion correctiva

- Si la verificacion falla, el `CR` vuelve a `En_Analisis` hasta completar informacion faltante o corregir inconsistencias.
- Si la validacion falla, el cambio se rechaza o se vuelve a negociar con nueva estimacion.
- Si al cierre falta actualizar `REQ`, matriz o pruebas, el `CR` no puede marcarse como `Implementado` o `Cerrado`.

## 8. Metricas de seguimiento

- 100% de solicitudes registradas como `CR` en un dia habil o menos.
- 100% de `CR` aprobados con evidencia escrita vinculada.
- 0 cambios implementados sin `CR` aprobado.
- 100% de `CR` aprobados con `REQ` y `CP` relacionados, o justificacion documentada de no aplicacion.

## 9. Trazabilidad y Documentos de Apoyo

1. `PAC/07-Control/TEMPLATE-CR.md`
2. `PAC/07-Control/CL-03_Verificacion_Cambios.md`
3. `PAC/02-Requisitos/PROC-02_Especificacion_Requerimientos.md`
4. `Proyecto/02-Requisitos/Matriz_Trazabilidad.md`
5. `PAC/07-Control/PROC-06_Inspecciones.md`
6. `Proyecto/07-Control/CR-01_Marcos_Dobles.md`, `CR-02_Tipos_Vidrio.md`, `CR-03_Maria_Luisa.md`, `CR-04_Pantalla_Secundaria.md` como referencias de casos reales.

## Historial de Cambios

| Version | Fecha | Autor | Descripcion |
| :-- | :-- | :-- | :-- |
| 1.0 | 2026-05-14 | Carlos Yonson | Reescritura inicial del proceso con enfoque ETVX. |
| 2.0 | 2026-05-17 | OpenCode | Refactor para separar PAC/Proyecto e incorporar verificacion, validacion y checklist completo del `CR`. |
