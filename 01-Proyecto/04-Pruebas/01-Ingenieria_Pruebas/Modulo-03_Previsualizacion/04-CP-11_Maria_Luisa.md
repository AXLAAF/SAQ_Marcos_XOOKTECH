# CP-11: Previsualizacion con Maria Luisa
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-11 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/09-REQ-09_Maria_Luisa|REQ-09 María Luisa]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/09-REQ-09_Maria_Luisa|REQ-09 María Luisa]]
- Change Request: [[05-Revisiones e inspecciones/01-Ingenieria_Control/10-CR-03_Maria_Luisa|CR-03 María Luisa]]
- Plan Maestro: [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*