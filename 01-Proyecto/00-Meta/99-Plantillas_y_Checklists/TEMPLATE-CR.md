---
id: CR-XXX
titulo: [Titulo del cambio]
origen: [WhatsApp / correo / minuta / reunion]
requisito_afectado: [[REQ-XXX_Nombre]]
estado: Pendiente # (Pendiente | En_Analisis | Aprobado | Rechazado | Implementado)
tipo_cambio: Modificacion # (Nuevo_Requerimiento | Modificacion | Correccion | Eliminacion)
solicitado_por: [Cliente o integrante]
fecha_solicitud: YYYY-MM-DD
prioridad: Media # (Alta | Media | Baja)
descripcion: [Resumen breve del cambio solicitado]
justificacion: [Motivo de negocio o tecnico]
impacto_alcance: [Modulos, documentos o acuerdos afectados]
impacto_tiempo_dias: 0
impacto_costo_mxn: 0
impacto_calidad: [Riesgos, pruebas o deuda tecnica esperada]
aprobado_por: ""
fecha_aprobacion: ""
evidencia_aprobacion: N/A
responsable_analisis: Samuel Blanco / Axel Morales
casos_prueba_requeridos:
  - [[CP-XX_Nombre]]
artefactos_afectados:
  - [[REQ-XXX_Nombre]]
  - [[02-Requisitos/Matriz_Trazabilidad]]
---

# CR-XXX: [Titulo del cambio]

> **Proceso relacionado**: [[PAC/07-Control/PROC-03_Control_Cambios]]

## 1. Descripcion General
[Explique que cambio se solicita, que comportamiento nuevo se espera y cual es el problema actual.]

## 2. Origen y Justificacion
- **Origen de la solicitud**: [Canal o documento donde surgio el cambio.]
- **Solicitado por**: [Nombre del cliente o integrante.]
- **Justificacion**: [Por que conviene realizar el cambio.]
- **Acuerdo o evidencia inicial**: [Minuta, correo, captura o referencia.]

## 3. Analisis de Impacto

### 3.1 Impacto en Alcance
- [REQ, modulo, pantalla, flujo o documento afectado.]

### 3.2 Impacto en Tiempo
- Dias adicionales estimados: [X]

### 3.3 Impacto en Costo
- Costo adicional estimado: $[X] MXN

### 3.4 Impacto en Calidad
- [Riesgos tecnicos, pruebas de regresion o validaciones extra.]

## 4. Decision y Aprobacion
- **Estado**: [Pendiente / En_Analisis / Aprobado / Rechazado / Implementado]
- **Aprobado por**: [Nombre]
- **Fecha de aprobacion**: [Fecha]
- **Evidencia de aprobacion**: [Archivo o N/A]
- **Observaciones de decision**: [Comentarios del cliente o del equipo.]

## 5. Seguimiento
- **Casos de prueba requeridos**: [[CP-XX_Nombre]]
- **Artefactos a actualizar**: [[REQ-XXX_Nombre]], [[02-Requisitos/Matriz_Trazabilidad]]
- **Responsable de implementacion**: [Nombre]
- **Fecha compromiso**: [Fecha objetivo si aplica]

## 6. Historial de Cambios

| Version | Fecha | Autor | Descripcion |
| :------ | :---- | :---- | :---------- |
| 1.0 | YYYY-MM-DD | [Nombre] | Creacion inicial |

---

*Ultima actualizacion: {{date}}*
