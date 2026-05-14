---
id: CP-11
titulo: Previsualizacion con Maria Luisa
modulo: Previsualizacion
tipo_prueba: Sistema
requerimiento: REQ-09_Maria_Luisa
version_sistema: "1.0"
estado: Pendiente
entrada: Foto cargada + marco seleccionado + Maria Luisa
precondiciones: Previsualizacion activa, catalogo de ML disponible
pasos:
  - 1. Cargar foto del cliente
  - 2. Seleccionar un marco
  - 3. Seleccionar una Maria Luisa
  - 4. Observar la previsualizacion
resultado_esperado: La previsualizacion muestra la Maria Luisa alrededor de la foto
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

# CP-11: Previsualizacion con Maria Luisa

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-11 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-09_Maria_Luisa]] |
| **Estado** | Pendiente (Scope Creep) |

## 2. Descripcion

Verificar que la seleccion de Maria Luisa se rendered correctamente en la previsualizacion.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Maria Luisa seleccionada | Diseno clasico |

## 4. Pasos de Ejecucion

1. Cargar foto de prueba
2. Seleccionar un marco
3. Abrir selector de Maria Luisa
4. Seleccionar un diseno
5. Observar previsualizacion

## 5. Resultado Esperado

- La Maria Luisa aparece alrededor de la foto
- El diseño se rendered correctamente
- Se actualiza el precio en la orden

## 6. Criterios de Exito

- [ ] ML visible en previsualizacion
- [ ] Precio actualizado
- [ ] Sin errores de renderizado

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-09_Maria_Luisa]]
- Change Request: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-03_Maria_Luisa]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*