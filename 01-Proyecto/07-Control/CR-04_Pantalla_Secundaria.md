---
id: CR-04
titulo: Change Request - Pantalla Secundaria
estado: Pendiente
tipo_cambio: Nuevo-Requerimiento
requerimiento_origen: REQ-10_Pantalla_Secundaria
solicitado_por: Cliente (Enmarcame - Geronimo)
fecha_solicitud: 2026-02-01
descripcion: El cliente pidio que la previsualizacion pueda verse en una pantalla secundaria (TV o monitor adicional) para que el cliente vea el resultado en una pantalla mas grande mientras el empleado opera el sistema.
impacto_tiempo_dias: 6
impacto_costo_mxn: 4000
aprobado_por: ""
fecha_aprobacion: ""
casos_prueba_requeridos:
  - CP-13_Proyeccion
  - CP-14_Sync_tiempo_real
  - CP-15_Fallback_sin_pantalla
referencias:
  - REQ-10_Pantalla_Secundaria
  - "01-Baseline/02-Acuerdos_Cliente.md - ACU-009"
tags:
  - cr/pendiente
  - scope-creep
---

# CR-04: Pantalla Secundaria

## 1. Informacion del Cambio

| Campo | Valor |
|-------|-------|
| **ID** | CR-04 |
| **Fecha de Solicitud** | 2026-02-01 |
| **Solicitado por** | Cliente (Enmarcame - Geronimo) |
| **Tipo de Cambio** | Nuevo Requerimiento |
| **Estado** | Pendiente de Aprobacion |

## 2. Descripcion del Cambio

### 2.1 Problema/Necesidad del Cliente

El cliente atiende a grupos familiares donde varios miembros quieren ver la previsualizacion al mismo tiempo. Actualmente solo una persona puede ver la pantalla de la computadora. Una pantalla adicional (TV) permitiria que toda la familia vea el resultado mientras el empleado opera.

### 2.2 Requerimiento Asociado

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-10_Pantalla_Secundaria]] - Requerimiento funcional asociado

### 2.3 Descripcion Tecnica

El sistema debe permitir:
- Detectar cuando se conecta una segunda pantalla
- Proyectar la previsualizacion en la pantalla secundaria
- Sincronizar en tiempo real (menos de 500ms) entre ambas pantallas
- Continuar funcionando si no hay pantalla secundaria
- Solo mostrar la previsualizacion (no la interfaz de control)

## 3. Impacto del Cambio

### 3.1 Impacto en Tiempo

| Actividad | Dias Estimados |
|-----------|----------------|
| Investigacion de API | 1 |
| Desarrollo frontend (deteccion de pantalla) | 1 |
| Desarrollo (sincronizacion) | 2 |
| Pruebas en multiples escenarios | 1.5 |
| Documentacion | 0.5 |
| **Total** | **6 dias** |

### 3.2 Impacto en Costo

| Concepto | Monto (MXN) |
|----------|-------------|
| Desarrollo | $3,000 |
| Pruebas | $1,000 |
| **Total** | **$4,000** |

> **Nota**: Este costo NO esta incluido en el acuerdo original de $24,000 MXN. Es un cargo adicional por Scope Creep. Adicionalmente, el cliente necesita invertir en hardware (TV o monitor adicional).

## 4. Analisis de Riesgo

| Riesgo | Probabilidad | Impacto | Mitigacion |
|--------|--------------|---------|------------|
| Compatibilidad con navegadores | Media | Alto | Pruebas en Chrome, Firefox, Edge |
| Latencia de sincronizacion | Baja | Alto | Optimizacion de rendimiento |
| Fallback cuando no hay pantalla | Alta | Bajo | Funcionamiento normal sin pantalla |
| Requerimientos de hardware | Baja | Medio | Documentar requisitos minimos |

## 5. Criterios de Aceptacion del Cambio

- [ ] El cliente aprueba formalmente el costo adicional de $4,000 MXN
- [ ] El cliente confirma que proporcionara la pantalla adicional (TV/monitor)
- [ ] Se define una fecha de entrega acordada
- [ ] Se documenta el alcance en un addendum al acuerdo original
- [ ] El equipo de desarrollo confirma el estimado de 6 dias

## 6. Requisitos de Hardware (Cliente)

| Equipo | Requerimiento Minimo | Costo Estimado |
|--------|---------------------|----------------|
| TV/Monitor secundario | HDMI, 32" o mayor | $2,000 - $5,000 MXN |
| Cable HDMI | Standard | $200 - $500 MXN |

> **Nota**: El costo del hardware NO esta incluido en los $4,000 MXN del cambio.

## 7. Aprobacion

| Campo | Valor |
|-------|-------|
| Elaborado por | Axel Adolfo Morales Caro |
| Fecha de elaboracion | 2026-03-23 |
| Estado | Pendiente de aprobacion |

### Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-03-23 | Axel Morales | Creacion inicial del CR |

---

*Change Request creado como parte del proceso de control de cambios (PROC-03)*
*Referencia: [[02-Acuerdos_Cliente]] - ACU-009*
*Este cambio requiere aprobacion formal del cliente antes de proceder*
*Prioridad: Baja - Requiere inversion adicional en hardware por parte del cliente*