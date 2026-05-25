# CP-09: Previsualizacion de marco doble
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-09 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/07-REQ-07_Marcos_Dobles|REQ-07 Marcos Dobles]] |
| **Estado** | Pendiente (Scope Creep) |

## 2. Descripcion

Verificar que la previsualizacion muestra dos fotografias dentro de un marco doble.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Imagen 1 | foto_cliente_1.jpg |
| Imagen 2 | foto_cliente_2.jpg |
| Marco seleccionado | Marco doble |

## 4. Pasos de Ejecucion

1. Cargar primera foto
2. Cargar segunda foto
3. Seleccionar marco doble
4. Observar previsualizacion

## 5. Resultado Esperado

- Ambas fotos visibles en el marco
- Cada foto en su espacio designado
- Marco renderizado correctamente

## 6. Criterios de Exito

- [ ] Dos imagenes visibles
- [ ] Marco doble renderizado
- [ ] Sin errores de renderizado

## 7. Trazabilidad

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/07-REQ-07_Marcos_Dobles|REQ-07 Marcos Dobles]]
- Change Request: [[05-Control de cambios/01-Ingenieria_Control/08-CR-01_Marcos_Dobles|CR-01 Marcos Dobles]]
- Plan Maestro: [[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*