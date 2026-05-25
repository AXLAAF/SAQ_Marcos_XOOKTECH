# Acuerdos con el Cliente - Proyecto Visualizador de Marcos
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Acuerdos del Cliente e Información Inicial
**Salidas:** Línea Base del Proyecto Certificada

---

> Documento que registra todos los acuerdos identificados con el cliente "Enmarcame" durante el desarrollo del proyecto. Incluye tanto los acuerdos respaldados por el contrato formal ([[01-Baseline/06-Contrato_Desarrollo]]) como los acuerdos verbales complementarios, con el contexto de cada acuerdo y su estado actual.

Artefacto de salida del Paso 4 de [[01-Baseline/00-PROC-01_Recuperacion_Linea_Base]]. Integra clausulas contractuales y acuerdos operativos verbales en un registro unico y trazable. Prerequisito para evaluar alcance en [[05-Control de cambios/05-PROC-05_Control_Configuracion|PROC-07 Gestión de Control]].

---

> [!IMPORTANT]
> Con la integracion del contrato formal ([[01-Baseline/06-Contrato_Desarrollo]]), los acuerdos ACU-006 a ACU-009 **ya no son scope creep puro** sino obligaciones contractuales formalizadas en la clausula PRIMERA del contrato. El nombre oficial del cliente es **Cliente**.

## 1. Registro de Acuerdos

### Acuerdo 1: Alcance del Proyecto

| Campo              | Descripcion                                                                                                                       |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| **ID**             | ACU-001                                                                                                                           |
| **Fecha**          | Enero 2026                                                                                                                        |
| **Contexto**       | Primera reunion en la tienda con Cliente                                                                                       |
| **Participantes**  | Líder SQA, Analista Técnico, Cliente, hijo de Cliente                                                                       |
| **Acuerdo**        | El sistema permitira a los clientes subir su foto, seleccionar un marco del catalogo y ver una previsualizacion 3D en tiempo real |
| **Detalles**       | No existio documento formal. Todo quedo en acuerdo verbal durante la reunion de 2 horas.                                          |
| **Estado**         | Implementado - Sistema en test                                                                                                    |
| **Monto asociado** | Incluido en los $------ MXN                                                                                                        |
| **Para que se documenta:** | Sirve como linea base para evaluar si REQ-07 a REQ-10 son cambios fuera de alcance que requieren CR formal. |

---

### Acuerdo 2: Costo de Desarrollo

| Campo             | Descripcion                                                       |
| ----------------- | ----------------------------------------------------------------- |
| **ID**            | ACU-002                                                           |
| **Fecha**         | Febrero 2026                                                      |
| **Contexto**      | Primera reunion - discusion de precio                             |
| **Participantes** | Líder SQA, Cliente                                         |
| **Acuerdo**       | El costo total del desarrollo sera de ------MXN (pesos mexicanos) |
| **Detalles**      | Pago unico. No sepidio enganche ni parcialidades.                 |
| **Estado**        | Pagado - Completado                                               |
| **Monto**         | $------ MXN                                                       |
| **Para que se documenta:** | Establece el compromiso economico original para distinguir entre costo incluido y adicionales por cambios (CR-01 a CR-04). |

---

### Acuerdo 3: Catalogo de Marcos

| Campo              | Descripcion                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| **ID**             | ACU-003                                                                                                                              |
| **Fecha**          | Febrero 2026                                                                                                                         |
| **Contexto**       | Discusion sobre el contenido del catalogo                                                                                            |
| **Participantes**  | Líder SQA, Analista Técnico, Cliente                                                                                              |
| **Acuerdo**        | El catalogo incluira todos los marcos disponibles en el inventario de la tienda                                                      |
| **Detalles**       | Líder SQA, Analista Técnico proporciono un Excel con aproximadamente con mas de 1000 marcos, se escanearon todos los marcos existentes en el local. |
| **Estado**         | Implementado + 1000 marcos                                                                                                           |
| **Monto asociado** | Incluido en los $------ MXN                                                                                                          |
| **Para que se documenta:** | Define el alcance del catalogo original para evaluar si ampliaciones (tipos de vidrio, maria luisa) requieren CR formal. |

---

### Acuerdo 4: Renta Mensual del Sistema

| Campo | Descripcion |
|-------|-------------|
| **ID** | ACU-004 |
| **Fecha**          | [PENDIENTE - fecha por verificar con Líder SQA. Proyecto inicio Enero 2026.]                                                         |
| **Contexto** | Discusion sobre el modelo de negocio recurrentes |
| **Participantes** | Líder SQA, Cliente |
| **Acuerdo** | El cliente pagara $2,500 MXN mensuales por el mantenimiento y uso del sistema |
| **Detalles** | Desglose segun contrato ([[01-Baseline/06-Contrato_Desarrollo]], clausula QUINTA): $2,000 renta del software + $500 servidor. Incluye hosting, mantenimiento de base de datos, soporte basico. Formalizado en contrato. |
| **Estado** | Activo - Pagando mensualmente |
| **Monto** | $2,500 MXN/mes ($2,000 renta + $500 servidor) |
| **Respaldo** | Clausula QUINTA del contrato ([[01-Baseline/06-Contrato_Desarrollo]]) |

---

### Acuerdo 5: Capacitacion

| Campo | Descripcion |
|-------|-------------|
| **ID** | ACU-005 |
| **Fecha** | Julio 2025 (aproximado) |
| **Contexto** | Antes del lanzamiento del sistema |
| **Participantes** | Líder SQA, Cliente, hijo de Cliente |
| **Acuerdo** | Se proporcionara una sesion de capacitacion para que los empleados puedan operar el sistema |
| **Detalles** | Capacitacion presencial de aproximadamente 1 hora. |
| **Estado** | Completado |
| **Monto asociado** | Incluido en los $24,000 MXN |
| **Para que se documenta:** | Registra entrega completa del alcance original para cerrar PROC-01 sin deudas pendientes. |

---

## 2. Acuerdos Formalizados en Contrato (antes clasificados como Scope Creep)

> **Nota:** Con la existencia del contrato formal ([[01-Baseline/06-Contrato_Desarrollo]]), las siguientes funcionalidades **son obligaciones contractuales** definidas en la clausula PRIMERA, no scope creep. Se mantiene el registro historico de como fueron identificadas originalmente.

### Acuerdo 6: Marcos Dobles

| Campo             | Descripcion                                                                            |
| ----------------- | -------------------------------------------------------------------------------------- |
| **ID**            | ACU-006                                                                                |
| **Fecha**         | 2026 (despues la implementacion del catalogo de marcos)                                |
| **Contexto**      | El cliente solicito vía presencial la funcionalidad de marcos dobles                   |
| **Participantes** | Líder SQA, Cliente                                                              |
| **Acuerdo**       | Pendiente de formalizar                                                                |
| **Detalles**      | No hay acuerdo formal de alcance, tiempo o costo. El cliente espera que se implemente. |
| **Estado**        | Pendiente - Sin aprobacion formal                                                      |
| **REQ asociada**  | REQ-07                                                                                 |
| **CR asociada**   | CR-01                                                                                  |
| **Para que se documenta:** | Identifica scope creep inicial para formalizar CR-01 con estimacion de costo y tiempo. |

---

### Acuerdo 7: Tipos de Vidrio

| Campo             | Descripcion                                                         |
| ----------------- | ------------------------------------------------------------------- |
| **ID**            | ACU-007                                                             |
| **Fecha**         | 2026 (despues de la implementacion del catalogo de marcos)          |
| **Contexto**      | El cliente solicito via presencial poder seleccionar tipo de vidrio |
| **Participantes** | Líder SQA, Cliente                                           |
| **Acuerdo**       | Pendiente de formalizar                                             |
| **Detalles**      | No hay acuerdo formal de alcance, tiempo o costo.                   |
| **Estado**        | Pendiente - Sin aprobacion formal                                   |
| **REQ asociada**  | REQ-08                                                              |
| **CR asociada**   | CR-02                                                               |
| **Para que se documenta:** | Documenta necesidad de ampliacion del catalogo para formalizar CR-02. |

---

### Acuerdo 8: Maria Luisa Multiple

| Campo             | Descripcion                                                                          |
| ----------------- | ------------------------------------------------------------------------------------ |
| **ID**            | ACU-008                                                                              |
| **Fecha**         | 2026 (despues de la implementacion del catalogo de marcos)                           |
| **Contexto**      | El cliente solicito via presencial poder seleccionar diferentes tipos de Maria Luisa |
| **Participantes** | Líder SQA, Cliente                                                            |
| **Acuerdo**       | Pendiente de formalizar                                                              |
| **Detalles**      | No hay acuerdo formal de alcance, tiempo o costo.                                    |
| **Estado**        | Pendiente - Sin aprobacion formal                                                    |
| **REQ asociada**  | REQ-09                                                                               |
| **CR asociada**   | CR-03                                                                                |
| **Para que se documenta:** | Registra expansion de opciones de maria luisa para CR-03. |

---

### Acuerdo 9: Pantalla Secundaria

| Campo             | Descripcion                                                                       |
| ----------------- | --------------------------------------------------------------------------------- |
| **ID**            | ACU-009                                                                           |
| **Fecha**         | 2026 (despues de la implementacion del catalogo de marcos)                        |
| **Contexto**      | El cliente pidio que la previsualizacion pudiera verse en una pantalla secundaria |
| **Participantes** | Líder SQA, Cliente                                                         |
| **Acuerdo**       | Pendiente de formalizar                                                           |
| **Detalles**      | No hay acuerdo formal de alcance, tiempo o costo.                                 |
| **Estado**        | Pendiente - Sin aprobacion formal                                                 |
| **REQ asociada**  | REQ-10                                                                            |
| **CR asociada**   | CR-04                                                                             |
| **Para que se documenta:** | Documenta necesidad de hardware adicional para CR-04. |

---

## 3. Resumen de Acuerdos

### 3.1 Acuerdos Formalizados (Completados)

| ID      | Descripcion                | Monto          | Estado     |
| ------- | -------------------------- | -------------- | ---------- |
| ACU-001 | Alcance del proyecto (MVP) | Incluido       | Completado |
| ACU-002 | Costo de desarrollo        | $_____ MXN     | -------    |
| ACU-003 | Catalogo de marcos         | Incluido       | Completado |
| ACU-004 | Renta mensual              | $2,500 MXN/mes | --------   |
| ACU-005 | Capacitacion               | Incluido       | Completado |

### 3.2 Acuerdos Pendientes de Formalizar

| ID | Descripcion | Estimado | Estado |
|----|-------------|----------|--------|
| ACU-006 | Marcos dobles | Por estimar | Pendiente |
| ACU-007 | Tipos de vidrio | Por estimar | Pendiente |
| ACU-008 | Maria Luisa multiple | Por estimar | Pendiente |
| ACU-009 | Pantalla secundaria | Por estimar | Pendiente |

---

## 4. Problemas Identificados

### 4.1 Falta de Formalizacion

| Problema | Impacto | Estado |
|----------|---------|--------|
| ~~No existe contrato escrito~~ | ~~Sin proteccion legal~~ | **RESUELTO** - Contrato firmado ([[01-Baseline/06-Contrato_Desarrollo]]) |
| Acuerdos operativos solo verbales | Detalles tecnicos dificiles de probar | Parcialmente resuelto - complementados por contrato |
| ~~Scope creep sin proceso~~ | ~~Confusion en expectativas~~ | **RESUELTO** - Funcionalidades formalizadas en contrato |

### 4.2 Recomendaciones

1. **Crear contrato formal** para todos los nuevos requerimientos
2. **Establecer proceso de control de cambios** (ya documentado en PROC-03)
3. **Obtener aprobacion escrita** del cliente antes de implementar cambios
4. **Documentar todas las conversaciones** via email o similares

---

## 5. Aprobacion

| Campo | Valor |
|-------|-------|
| Elaborado por | Analista Técnico |
| Revisado por | Líder SQA |
| Fecha de elaboracion | 2026-03-23 |
| Estado | Completado |

### Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-03-23 | Analista Técnico | Creacion inicial - Acuerdos recuperados |
| 1.1 | 2026-04-13 | Kilo-SQA-Agent | Vinculado al proceso PROC-01, agregados campos "Para que se documenta" en cada ACU, corregida fecha ACU-004 |
| 1.2 | 2026-04-14 | Analista Técnico | Integracion del contrato formal: actualizado nombre del cliente a Cliente, reclasificados ACU-006 a ACU-009 como obligaciones contractuales, actualizado desglose ACU-004, resueltos problemas de falta de formalizacion |

---

*Documento creado como parte del PROC-01 - Recuperacion de Linea Base*
*Referencia: [[09-Notes/01-Linea_Base-Original/05-Minuta_Entrevista|Minuta de Entrevista]], [[09-Notes/01-Linea_Base-Original/02-Propuesta_Recuperada|Propuesta Recuperada]]*