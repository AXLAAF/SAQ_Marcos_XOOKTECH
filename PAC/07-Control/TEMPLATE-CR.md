---
id: CR-XXX
titulo: [Titulo del cambio]
version: "1.0"
estado: Pendiente # Pendiente | En_Analisis | Aprobado | Rechazado | Implementado | Cerrado
tipo_cambio: Modificacion # Nuevo_Requerimiento | Modificacion | Correccion | Eliminacion
prioridad: Media # Alta | Media | Baja
solicitado_por: [Cliente o integrante]
fecha_solicitud: YYYY-MM-DD
origen: [WhatsApp | correo | minuta | reunion | hallazgo interno]
requisito_afectado: [REQ-XXX_Nombre o N/A]
descripcion: [Resumen del cambio solicitado]
justificacion: [Motivo comercial, funcional o tecnico]
impacto_alcance: [Modulos, pantallas, reglas o documentos afectados]
impacto_tiempo_dias: 0
impacto_costo_mxn: 0
impacto_calidad: [Riesgos, deuda tecnica, pruebas de regresion o validaciones necesarias]
riesgo_principal: [Riesgo mas importante del cambio]
decision: Pendiente # Pendiente | Aprobado | Rechazado | Requiere_Ajuste
aprobado_por: [Nombre o N/A]
fecha_aprobacion: YYYY-MM-DD
evidencia_aprobacion: [Ruta a correo, captura o minuta]
responsable_analisis: [Nombre]
responsable_implementacion: [Nombre o N/A]
casos_prueba_requeridos:
  - [CP-XX_Nombre]
artefactos_afectados:
  - [REQ-XXX_Nombre]
  - Proyecto/02-Requisitos/Matriz_Trazabilidad.md
resultado_verificacion: Pendiente # Pendiente | Aprobado | Requiere_Retrabajo
porcentaje_verificacion: 0
revisor_verificacion: [Nombre]
fecha_verificacion: YYYY-MM-DD
fecha_cierre: YYYY-MM-DD
---

# CR-XXX - [Titulo del cambio]

> Proceso relacionado: `PAC/07-Control/PROC-03_Control_Cambios.md`

## 1. Descripcion General

[Explique que se solicita cambiar, cual es el comportamiento actual y cual seria el comportamiento esperado.]

## 2. Contexto y Justificacion

| Campo | Valor |
| :-- | :-- |
| Origen de la solicitud | [Canal o documento] |
| Solicitado por | [Nombre] |
| Requerimiento afectado | [REQ-XXX_Nombre o N/A] |
| Justificacion | [Motivo del cambio] |

## 3. Analisis de Impacto

### 3.1 Alcance

- [Pantallas, procesos, reglas o entregables afectados]

### 3.2 Tiempo

- Dias adicionales estimados: [Numero]
- Supuestos del estimado: [Base del calculo]

### 3.3 Costo

- Costo adicional estimado: $[Monto] MXN
- Consideraciones comerciales: [Si esta incluido, si es extra o si requiere aprobacion adicional]

### 3.4 Calidad y Riesgo

- Riesgo principal: [Descripcion]
- Validaciones o pruebas requeridas: [Regresion, nuevas pruebas, inspecciones]

## 4. Trazabilidad

| Elemento | Referencia |
| :-- | :-- |
| REQ asociado | [REQ-XXX_Nombre] |
| Casos de prueba | [CP-XX_Nombre] |
| Artefactos afectados | [Lista de documentos o componentes] |
| Evidencia de origen | [Correo, captura o minuta] |

## 5. Verificacion del CR

| Campo | Valor |
| :-- | :-- |
| Checklist aplicado | `PAC/07-Control/CL-03_Verificacion_Cambios.md` |
| Resultado | [Aprobado / Requiere_Retrabajo] |
| Porcentaje | [0-100] |
| Revisor | [Nombre] |
| Fecha | [YYYY-MM-DD] |

## 6. Decision y Validacion

| Campo | Valor |
| :-- | :-- |
| Decision | [Aprobado / Rechazado / Requiere_Ajuste] |
| Aprobado por | [Nombre o N/A] |
| Fecha de aprobacion | [YYYY-MM-DD o N/A] |
| Evidencia de aprobacion | [Ruta o N/A] |
| Observaciones | [Comentario relevante del cliente o del equipo] |

## 7. Seguimiento e Implementacion

- **Responsable de implementacion:** [Nombre]
- **Fecha compromiso:** [YYYY-MM-DD]
- **Actualizacion requerida en REQ:** [Si / No - detalle]
- **Actualizacion requerida en pruebas:** [Si / No - detalle]
- **Actualizacion requerida en matriz de trazabilidad:** [Si / No - detalle]

## 8. Cierre

| Campo | Valor |
| :-- | :-- |
| Estado final | [Implementado / Rechazado / Cerrado] |
| Fecha de cierre | [YYYY-MM-DD] |
| Evidencia de cierre | [Commit, minuta, prueba o nota] |

## 9. Historial de Cambios

| Version | Fecha | Autor | Descripcion |
| :-- | :-- | :-- | :-- |
| 1.0 | YYYY-MM-DD | [Nombre] | Creacion inicial |
