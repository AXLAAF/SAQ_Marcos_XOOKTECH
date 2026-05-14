---
id: PROC-08
titulo: Proceso 8 - Control de Cambios (CR)
version: "2.0"
estado: Activo
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-14
responsable: Samuel Blanco (Lider) / Axel Morales (Analisis tecnico)
autor: Carlos Yonson / Axel Morales
disparador: Solicitud de cambio nueva o ajuste al alcance por parte del cliente o del equipo
criterio_entrada: Solicitud identificada y registrada en un CR con datos minimos de origen, impacto y responsable
criterio_salida: CR con estado documentado, evidencia de decision y artefactos actualizados cuando el cambio es aprobado
entradas:
  - [[00-Meta/05-PROC-01_Gestion_Documental]]
  - [[02-Requisitos/00-PROC-02_Especificacion_Requerimientos]]
  - [[02-Requisitos/01-STD-03_Matriz_Trazabilidad]]
salidas:
  - [[07-Control/08-CR-01_Marcos_Dobles]]
  - [[02-Requisitos/01-STD-03_Matriz_Trazabilidad]]
referencias_biblio:
  - "Galin, D. (2004). Software Quality Assurance: From theory to implementation."
  - "O'Regan, G. (2010). A Practical Approach to Software Quality."
  - "CMMI-CM (Configuration Management)"
tags:
  - meta/proceso
  - fase/control
  - tipo/proceso
  - estado/activo
---

# Proceso 8 - Control de Cambios (Change Requests)

> **Fundamentacion**: Este proceso adapta practicas de **CMMI-CM**, analisis de impacto y el modelo **ETVX** para evitar cambios ejecutados por memoria, reducir conflictos de costo y mantener trazabilidad entre solicitud, requerimiento, prueba e implementacion.

## 1. Proposito

Formalizar toda solicitud de cambio del proyecto **Visualizador de Marcos** para que el equipo pueda registrarla, analizar su impacto, aprobarla o rechazada con evidencia y actualizar la linea base del proyecto sin perder control del alcance.

## 2. Alcance

- Aplica a cambios solicitados por el cliente, hallazgos del equipo y ajustes que afecten alcance, tiempo, costo, calidad o trazabilidad.
- Cubre desde el registro inicial del cambio hasta la actualizacion del requerimiento, pruebas y evidencia de aprobacion.
- No autoriza implementacion inmediata: ningun cambio debe pasar a desarrollo sin analisis y decision registrada.

## 3. Diagnostico del Proceso Actual (Por Carlos Yonson)

**Hallazgos relevantes:**
- Falta de registro formal y consecutivo de CR (Change Request).
- Falta de análisis de impacto antes de comprometer esfuerzo.
- Falta de evidencia escrita de aprobación o rechazo.
- Falta de relación explicita entre cambio, REQ afectado y pruebas que deben actualizarse.

## 4. Estructura del Proceso (Modelo ETVX)

| Etapa | Entry | Task | Verification | Exit | Responsable |
| :-- | :-- | :-- | :-- | :-- | :-- |
| **Registro** | Solicitud identificada en WhatsApp, correo o reunion | Crear `CR-XX_Nombre.md`, asignar ID, capturar origen | Samuel revisa datos minimos | CR en estado `Pendiente` | Samuel |
| **Analisis** | CR registrado + acuerdos base + REQ afectados | Estimar impacto en alcance, tiempo, costo y calidad | Axel valida impacto explicito | CR con analisis completo | Axel |
| **Aprobacion** | CR analizado y listo para decision | Presentar impacto al cliente y documentar decision | Existe evidencia escrita (captura/correo) | CR `Aprobado` o `Rechazado` | Samuel + Cliente |
| **Implementacion**| CR aprobado + REQ y plan actualizados | Ejecutar el cambio referenciando el ID del CR | Verificacion de implementacion vs CR | Cambio implementado | Axel |
| **Cierre** | Cambio validado o rechazo documentado | Actualizar REQ, Matriz de Trazabilidad y CP | Linea base refleja decision final | CR cerrado y trazable | Samuel + Axel |

## 5. Notas Tecnicas de Mejora (NT)

- **NT-1: Registro el mismo dia.** Evita perdida de contexto y acuerdos verbales sin rastro.
- **NT-2: Analisis de impacto.** Ningun cambio se promete sin revisar alcance/tiempo/costo.
- **NT-3: Aprobacion por escrito.** Captura de WhatsApp o correo vinculada al CR para evitar conflictos.
- **NT-4: Implementacion controlada.** Solo CRs aprobados pasan a desarrollo.
- **NT-5: Trazabilidad completa.** El cierre exige actualizar REQ y Matriz de Trazabilidad.

## 6. Casos Actuales Registrados

| ID | Titulo | Estado | Referencia |
| :-- | :-- | :-- | :-- |
| CR-01 | Marcos Dobles | Pendiente | [[07-Control/08-CR-01_Marcos_Dobles]] |
| CR-02 | Tipos de Vidrio | Pendiente | [[07-Control/09-CR-02_Tipos_Vidrio]] |
| CR-03 | Maria Luisa Multiple | Pendiente | [[07-Control/10-CR-03_Maria_Luisa]] |
| CR-04 | Pantalla Secundaria | Pendiente | [[07-Control/11-CR-04_Pantalla_Secundaria]] |

## 7. Metricas de Calidad

- **Registro**: 100% de solicitudes en CR en menos de 24h.
- **Analisis**: 100% de CR con impacto documentado antes de decision.
- **Disciplina**: 0 cambios implementados sin CR aprobado.

---
*Refinamiento de Proceso: Carlos Yonson (2026-05-14) | Integracion de Gobernanza: Axel Morales (2026-05-14)*
