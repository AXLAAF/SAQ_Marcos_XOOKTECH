# CP-13: Proyeccion en pantalla secundaria

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-13 |
| **Modulo** | Pantalla Secundaria (Modulo-04) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-10_Pantalla_Secundaria]] |
| **Estado** | Pendiente (Scope Creep) |

## 2. Descripcion

Verificar que el sistema puede proyectar la previsualizacion en una pantalla secundaria cuando esta conectada.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Pantalla secundaria | TV 32" via HDMI |
| Contenido esperado | Solo previsualizacion (sin UI) |

## 4. Pasos de Ejecucion

1. Conectar TV via HDMI
2. Abrir el sistema
3. Seleccionar "Proyectar en pantalla secundaria"
4. Observar la TV

## 5. Resultado Esperado

- El sistema detecta la pantalla secundaria
- Pregunta si desea proyectar
- La previsualizacion aparece en la TV
- La interfaz de control NO aparece en la TV

## 6. Criterios de Exito

- [ ] Pantalla detectada
- [ ] Proyeccion iniciada
- [ ] Solo previsualizacion visible

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-10_Pantalla_Secundaria]] - CA-01
- Change Request: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-04_Pantalla_Secundaria]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01-Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*
