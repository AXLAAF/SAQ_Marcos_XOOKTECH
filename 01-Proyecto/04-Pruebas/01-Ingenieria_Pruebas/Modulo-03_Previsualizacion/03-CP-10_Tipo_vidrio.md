# CP-10: Previsualizacion con tipo de vidrio
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-10 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/08-REQ-08_Tipo_Vidrio|REQ-08 Tipo de Vidrio]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/08-REQ-08_Tipo_Vidrio|REQ-08 Tipo de Vidrio]]
- Change Request: [[05-Control de cambios/01-Ingenieria_Control/09-CR-02_Tipos_Vidrio|CR-02 Tipos de Vidrio]]
- Plan Maestro: [[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*