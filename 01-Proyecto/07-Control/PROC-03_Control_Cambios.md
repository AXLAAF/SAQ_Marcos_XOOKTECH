---
id: PROC-03
nombre: Proceso de Control de Cambios
titulo: Proceso 3 - Control de Cambios
version: "1.0"
fecha: 2026-05-14
fecha_creacion: 2026-05-14
ultima_revision: 2026-05-14
autor: Carlos Yonson
basado_en: CMMI-CM, ETVX, Analisis de Impacto
estado: Propuesto
tipo: Proceso
responsable: Samuel Blanco (Lider) / Axel Morales (Analisis tecnico)
disparador: Solicitud de cambio nueva o ajuste al alcance por parte del cliente o del equipo
criterio_entrada: Solicitud identificada y registrada en un CR con datos minimos de origen, impacto y responsable
criterio_salida: CR con estado documentado, evidencia de decision y artefactos actualizados cuando el cambio es aprobado
entradas:
  - 01-Linea_Base/03-Acuerdos_Cliente.md
  - 02-Requisitos/PROC-02_Especificacion_Requerimientos.md
  - 02-Requisitos/Matriz_Trazabilidad.md
  - 00-Meta/99-Plantillas_y_Checklists/TEMPLATE-CR.md
salidas:
  - 07-Control/CR-XX_Nombre.md
  - 02-Requisitos/Matriz_Trazabilidad.md
  - Evidencia de aprobacion del cliente
  - Casos de prueba actualizados
notacion: "NT: indica una Nota Tecnica con sugerencia de mejora al proceso."
---

# Proceso 3 - Control de Cambios

> **Fundamentacion**: Este proceso adapta practicas de **CMMI-CM**, analisis de impacto y el modelo **ETVX** para evitar cambios ejecutados por memoria, reducir conflictos de costo y mantener trazabilidad entre solicitud, requerimiento, prueba e implementacion.

## 1. Proposito

Formalizar toda solicitud de cambio del proyecto **Visualizador de Marcos** para que el equipo pueda registrarla, analizar su impacto, aprobarla o rechazarla con evidencia y actualizar la linea base del proyecto sin perder control del alcance.

## 2. Alcance

- Aplica a cambios solicitados por el cliente, hallazgos del equipo y ajustes que afecten alcance, tiempo, costo, calidad o trazabilidad.
- Cubre desde el registro inicial del cambio hasta la actualizacion del requerimiento, pruebas y evidencia de aprobacion.
- Incluye cambios funcionales, correcciones de alcance, ampliaciones no contempladas y decisiones de no implementar.
- No autoriza implementacion inmediata: ningun cambio debe pasar a desarrollo sin analisis y decision registrada.

## 3. Diagnostico del Proceso Actual

**Actualmente:**
- El cliente comunica cambios por WhatsApp, llamada o durante la operacion diaria.
- La solicitud puede quedar solo en la conversacion y no en un artefacto formal del vault.
- No siempre se analiza el impacto en tiempo, costo, pruebas y requerimientos afectados antes de prometer una entrega.
- Los cambios extra se mezclan con el alcance original, lo que genera discusiones sobre si un ajuste ya estaba incluido o debe cobrarse aparte.

Los hallazgos mas relevantes del diagnostico son:

- Falta de registro formal y consecutivo de CR (Change Request).
- Falta de análisis de impacto antes de comprometer esfuerzo.
- Falta de evidencia escrita de aprobación o rechazo.
- Falta de relación explicita entre cambio, REQ afectado y pruebas que deben actualizarse.

## 4. Justificación Teórica

### 4.1 CMMI-CM

CMMI para Gestion de Configuracion establece que un cambio debe identificarse, evaluarse, aprobarse y rastrearse antes de modificar la linea base. En este proyecto la linea base no solo es el codigo: tambien incluye acuerdos con el cliente, requerimientos y casos de prueba.

### 4.2 Analisis de Impacto

El analisis de impacto obliga a responder, antes de implementar, que artefactos cambian, cuanto tiempo adicional se necesita, si existe costo extra y que riesgo se introduce. Esto reduce retrabajo y discusiones posteriores.

### 4.3 Modelo ETVX

El modelo ETVX vuelve repetible el proceso porque define con claridad la entrada del cambio, las tareas minimas, la verificacion requerida y la salida aceptable en cada etapa.

### 4.4 Control de Versiones

El control de cambios documental debe conectarse con el repositorio del sistema. Todo cambio aprobado debe poder rastrearse hasta el artefacto tecnico que lo implementa, ya sea un commit, una rama, una entrega o una nota de actualizacion del repositorio `Marcos2`.

## 5. Roles y Responsabilidades

| Rol | Responsable | Responsabilidades |
| :-- | :-- | :-- |
| Negocio y seguimiento | Samuel Blanco | Recibe la solicitud, la registra o valida su registro, presenta impacto al cliente y resguarda la aprobacion o rechazo. |
| Analisis tecnico | Axel Morales | Evalua impacto en requerimientos, pruebas, tiempo, costo tecnico y riesgo; define artefactos afectados y seguimiento tecnico. |
| Solicitante y aprobador | Cliente | Explica la necesidad, aclara prioridades, acepta o rechaza el impacto y confirma por escrito la decision. |

## 6. Entradas y Salidas

### Entradas

| Entrada | Uso dentro del proceso |
| :-- | :-- |
| [[01-Linea_Base/03-Acuerdos_Cliente]] | Delimitar que estaba dentro y fuera del alcance original. |
| [[02-Requisitos/PROC-02_Especificacion_Requerimientos]] | Identificar el requerimiento afectado y sus criterios de aceptacion. |
| [[02-Requisitos/Matriz_Trazabilidad]] | Revisar relaciones entre REQ, CR y CP antes de aprobar el cambio. |
| [[00-Meta/99-Plantillas_y_Checklists/TEMPLATE-CR]] | Registrar el cambio con formato minimo comun. |
| Solicitud del cliente o del equipo | Activar el proceso con el contexto inicial del cambio. |

### Salidas

| Salida | Resultado esperado |
| :-- | :-- |
| [[CR-01_Marcos_Dobles]], [[CR-02_Tipos_Vidrio]], [[CR-03_Maria_Luisa]], [[CR-04_Pantalla_Secundaria]] | Ejemplos vivos de solicitudes de cambio con trazabilidad. |
| `CR-XX_Nombre.md` | Registro formal de cualquier nuevo cambio. |
| REQ actualizado | Requerimiento ajustado cuando el cambio es aprobado. |
| Matriz de trazabilidad actualizada | Relacion explicita entre CR, REQ y CP. |
| Evidencia de aprobacion | Captura, correo o mensaje vinculado al cambio. |

## 7. Flujo ETVX

| Etapa | Entry | Task | Verification | Exit | Responsable |
| :-- | :-- | :-- | :-- | :-- | :-- |
| Registro | Solicitud identificada en WhatsApp, correo, reunion o hallazgo interno | Crear `CR-XX_Nombre.md`, asignar ID, capturar origen, solicitante, cambio y REQ afectado | Samuel revisa que existan datos minimos y que el cambio no quede solo en conversacion | CR en estado `Pendiente` o `En_Analisis` | Samuel |
| Analisis | CR registrado + acuerdos base + REQ afectados | Estimar impacto en alcance, tiempo, costo, calidad y pruebas; identificar artefactos afectados | Axel valida que el impacto sea explicito y que existan REQ/CP relacionados | CR con analisis completo | Axel |
| Aprobacion | CR analizado y listo para decision | Presentar impacto al cliente y documentar aprobacion o rechazo | Existe evidencia escrita de la decision y estado actualizado | CR en estado `Aprobado` o `Rechazado` | Samuel + Cliente |
| Implementacion | CR aprobado + REQ y plan actualizados | Programar o ejecutar el cambio, referenciando el ID del CR en el trabajo tecnico | El equipo confirma que la implementacion, pruebas y evidencia apuntan al CR correcto | Cambio implementado o programado sin ambiguedad | Axel / Samuel |
| Actualizacion de linea base | Cambio implementado y validado, o rechazo documentado | Actualizar REQ, matriz de trazabilidad, CP y notas de entrega; cerrar el CR | La linea base documental y tecnica refleja la decision final | CR cerrado y trazable | Samuel + Axel |

## 8. Proceso Detallado (Actualmente vs Propuesta)

### Paso 1: Registro del Cambio (Planear)

**Actualmente:**
- La solicitud puede quedarse perdida en mensajes o sólo en la memoria del equipo.
- El cambio a veces se comenta primero y se documenta después, o no se documenta.

**NT-1:** Toda solicitud debe convertirse el mismo día en un archivo `CR-XX_Nombre.md` basado en [[00-Meta/99-Plantillas_y_Checklists/TEMPLATE-CR]]. Esto evita que un acuerdo verbal se convierta en trabajo sin rastro.

**Propuesta:**
- Samuel registra el cambio en la carpeta `07-Control/`.
- Asigna ID consecutivo y estado inicial `Pendiente`.
- Se captura el origen real de la solicitud y el `REQ` afectado.

### Paso 2: Análisis de Impacto (Hacer)

**Actualmente:**
- El esfuerzo se estima de forma rápida o intuitiva.
- No siempre se identifica si el cambio afecta pruebas, reglas de negocio o acuerdos previos.

**NT-2:** Ningun cambio debe prometerse al cliente sin una revision minima de impacto en alcance, tiempo, costo y calidad. El analisis debe dejar claro que parte del sistema cambia y que pruebas deben ajustarse.

**Propuesta:**
- Axel revisa el CR junto con el REQ y la matriz de trazabilidad.
- Documenta `impacto_alcance`, `impacto_tiempo_dias`, `impacto_costo_mxn` e `impacto_calidad`.
- Se listan artefactos y casos de prueba afectados.

### Paso 3: Aprobacion del Cliente (Verificar)

**Actualmente:**
- El cliente puede decir "si" por mensaje o asumir que el cambio estaba incluido.
- No existe una regla fija para diferenciar aceptacion verbal de aprobacion formal.

**NT-3:** Toda decision debe quedar por escrito. Una captura de WhatsApp, correo o minuta validada es suficiente, siempre que este vinculada al CR.

**Propuesta:**
- Samuel presenta el impacto al cliente con alcance, tiempo y costo.
- El cliente aprueba o rechaza por escrito.
- El CR actualiza `estado`, `aprobado_por`, `fecha_aprobacion` y `evidencia_aprobacion`.

### Paso 4: Implementacion Controlada (Actuar)

**Actualmente:**
- El equipo podria comenzar a resolver el cambio en cuanto parece claro tecnicamente.
- La implementacion puede adelantarse antes de que el alcance quede cerrado.

**NT-4:** Solo los CR aprobados pasan a implementacion. El ID del CR debe aparecer en el trabajo tecnico asociado para que el repositorio y la documentacion hablen del mismo cambio.

**Propuesta:**
- Axel y Samuel coordinan la implementacion solo despues de la aprobacion.
- El cambio se vincula con el trabajo tecnico correspondiente y con las pruebas a actualizar.
- Si el cambio no es aprobado, no se implementa y el CR se cierra con causa.

### Paso 5: Actualizacion de Linea Base y Cierre

**Actualmente:**
- El CR puede existir, pero la trazabilidad con REQ y CP no siempre se actualiza al cierre.
- El cambio aprobado puede quedar implementado sin reflejarse en toda la documentacion.

**NT-5:** El cierre del CR debe incluir actualizacion de requerimientos, matriz de trazabilidad, pruebas y evidencia final. Sin esto, el cambio existe en el sistema pero no en la linea base.

**Propuesta:**
- Se actualizan los REQ afectados, los CP relacionados y la matriz de trazabilidad.
- El CR pasa a `Implementado` o se mantiene en `Aprobado` hasta que exista evidencia de despliegue.
- El expediente del cambio queda completo para inspeccion o auditoria.

## 9. Plantilla de CR

La plantilla oficial del proceso es [[00-Meta/99-Plantillas_y_Checklists/TEMPLATE-CR]]. Todo CR debe contener como minimo los siguientes campos:

- `id`
- `titulo`
- `origen`
- `requisito_afectado`
- `estado`
- `tipo_cambio`
- `solicitado_por`
- `fecha_solicitud`
- `prioridad`
- `descripcion`
- `justificacion`
- `impacto_alcance`
- `impacto_tiempo_dias`
- `impacto_costo_mxn`
- `impacto_calidad`
- `aprobado_por`
- `fecha_aprobacion`
- `evidencia_aprobacion`
- `casos_prueba_requeridos`
- `artefactos_afectados`

Ejemplos vivos del formato:

- [[CR-01_Marcos_Dobles]]
- [[CR-02_Tipos_Vidrio]]
- [[CR-03_Maria_Luisa]]
- [[CR-04_Pantalla_Secundaria]]

## 10. Metricas de Exito

- **Registro oportuno**: 100% de las solicitudes identificadas en un CR dentro de 1 dia habil.
- **Analisis completo**: 100% de los CR con impacto en alcance, tiempo, costo y calidad antes de presentar al cliente.
- **Formalidad**: 100% de los CR aprobados o rechazados con evidencia escrita vinculada.
- **Disciplina de implementacion**: 0 cambios implementados sin CR aprobado.
- **Trazabilidad**: 100% de los CR aprobados enlazados con al menos un REQ y un CP o evidencia de no requerir pruebas nuevas.

## 11. Ejemplo Aplicado: CR-01 Marcos Dobles

| Campo | Valor |
| :-- | :-- |
| Caso | [[CR-01_Marcos_Dobles]] |
| Origen | Solicitud del cliente recuperada en `ACU-006` y conversaciones operativas |
| Requerimiento afectado | [[REQ-07_Marcos_Dobles]] |
| Impacto en tiempo | 5 dias |
| Impacto en costo | $3,000 MXN |
| Prueba afectada | [[05-Pruebas/Modulo-03_Previsualizacion/CP-09_Marco_doble]] |
| Estado actual | Pendiente de aprobacion |

Aplicacion del proceso en este caso:

1. El cambio se registra como `CR-01` para evitar que la funcionalidad se trate como alcance original.
2. Axel estima el esfuerzo y el riesgo tecnico sobre la previsualizacion y pruebas.
3. Samuel presenta el costo y tiempo adicional al cliente para aprobacion.
4. Solo si el cliente aprueba por escrito se actualiza `REQ-07`, la matriz de trazabilidad y `CP-09`.

## 12. Integracion con Otros Procesos

- **Requisitos**: Un CR aprobado debe reflejarse en [[02-Requisitos/PROC-02_Especificacion_Requerimientos]] y en el REQ afectado para que los criterios de aceptacion no queden obsoletos.
- **Pruebas**: [[05-Pruebas/PROC-05_Plan_Pruebas]] recibe el CR aprobado como entrada para crear o actualizar CP y para definir regresiones necesarias.
- **Control de versiones**: La implementacion del cambio debe referenciar el ID del CR en el trabajo tecnico del repositorio `Marcos2`, para poder rastrear que se cambio y por que.

## 13. Aprobacion

| Rol | Nombre | Firma / Confirmacion | Fecha |
| :-- | :-- | :-- | :-- |
| Lider de negocio | Samuel Blanco | ____________________ | ____________________ |
| Analisis tecnico | Axel Morales | ____________________ | ____________________ |
| Cliente | Enmarcame / Representante | ____________________ | ____________________ |

## 14. Justificacion de Mejoras

**NT-1: Registro el mismo dia del cambio.**  
Justificacion: Disminuye la perdida de contexto y evita que el equipo trabaje con instrucciones parciales o recuerdos incompletos.

**NT-2: Analisis explicito de impacto.**  
Justificacion: Permite negociar con datos y evita comprometer tiempo o costo sin comprender el alcance real del cambio.

**NT-3: Aprobacion por escrito.**  
Justificacion: Reduce conflictos con el cliente y deja evidencia suficiente para auditoria o aclaracion comercial posterior.

**NT-4: Implementacion solo despues de aprobar.**  
Justificacion: Protege al equipo de retrabajo y conserva el control de configuracion sobre la linea base acordada.

**NT-5: Cierre con trazabilidad completa.**  
Justificacion: Garantiza que lo aprobado, lo implementado y lo probado coincidan en los documentos del proyecto.

## 15. Referencias y Documentos de Apoyo

1. [[00-Meta/99-Plantillas_y_Checklists/TEMPLATE-CR]] - Plantilla oficial para registrar cambios.
2. [[02-Requisitos/PROC-02_Especificacion_Requerimientos]] - Proceso que recibe la actualizacion del alcance aprobado.
3. [[05-Pruebas/PROC-05_Plan_Pruebas]] - Proceso que define los casos de prueba derivados del cambio.
4. [[02-Requisitos/Matriz_Trazabilidad]] - Registro de relaciones entre REQ, CR y CP.
5. [[CR-01_Marcos_Dobles]], [[CR-02_Tipos_Vidrio]], [[CR-03_Maria_Luisa]], [[CR-04_Pantalla_Secundaria]] - Casos actuales del proyecto.
6. CMMI for Development - Configuration Management (CM).
7. SWEBOK - Software Configuration Management y Software Requirements.

## Historial de Cambios

| Version | Fecha      | Autor         | Descripcion                                                                                                                    |
| :------ | :--------- | :------------ | :----------------------------------------------------------------------------------------------------------------------------- |
| 1.0     | 2026-05-14 | Carlos Yonson | Reescritura completa del proceso de control de cambios con diagnostico, flujo ETVX, plantilla CR, metricas y ejemplo aplicado. |
