---
id: CP-10
titulo: Previsualizacion con tipo de vidrio
modulo: Previsualizacion
tipo_prueba: Sistema
requerimiento: REQ-08_Tipo_Vidrio
version_sistema: "1.0"
estado: Pendiente
entrada: Foto cargada + marco seleccionado + tipo de vidrio
precondiciones: Previsualizacion activa, marco seleccionado
pasos:
  - 1. Cargar foto del cliente
  - 2. Seleccionar un marco
  - 3. Seleccionar tipo de vidrio (antirreflejo)
  - 4. Observar la previsualizacion
resultado_esperado: La previsualizacion muestra el efecto del vidrio seleccionado
resultado_actual: ""
paso_fallo: ""
severidad_defecto: ""
fecha_ejecucion: ""
responsable: ""
tags:
  - cp/pendiente
  - modulo/previsualizacion
  - req/pendiente
  - scope-creep
---

# CP-10: Previsualizacion con tipo de vidrio

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-10 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-08_Tipo_Vidrio]] |
| **Estado** | Pendiente (Scope Creep) |

## 2. Descripcion

Verificar que la seleccion de tipo de vidrio se refleja en la previsualizacion.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Tipo de vidrio | Antirreflejo (+$150 MXN) |

## 4. Pasos de Ejecucion

1. Cargar foto de prueba
2. Seleccionar un marco
3. Abrir selector de tipo de vidrio
4. Seleccionar "Antirreflejo"
5. Observar cambio visual

## 5. Resultado Esperado

- Se muestra indicador del tipo de vidrio seleccionado
- El precio se actualiza en la orden
- La previsualizacion puede mostrar un efecto visual

## 6. Criterios de Exito

- [ ] Tipo de vidrio seleccionado
- [ ] Precio actualizado
- [ ] Orden generada correctamente

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-08_Tipo_Vidrio]]
- Change Request: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-02_Tipos_Vidrio]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*