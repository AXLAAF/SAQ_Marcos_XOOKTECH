# CP-14: Sincronizacion en tiempo real entre pantallas
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-14 |
| **Modulo** | Pantalla Secundaria (Modulo-04) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria|REQ-10 Pantalla Secundaria]] |
| **Estado** | Pendiente (Scope Creep) |

## 2. Descripcion

Verificar que la sincronizacion entre la pantalla principal y la secundaria es en tiempo real (<500ms).

## 3. Criterio de Aceptacion

- CA-02: La sincronizacion entre pantallas es menor a 500ms

## 4. Pasos de Ejecucion

1. Iniciar proyeccion en pantalla secundaria
2. Cambiar el marco en pantalla principal
3. Cronometrar tiempo hasta que se actualice la secundaria
4. Repetir 5 veces y promediar

## 5. Resultado Esperado

- Actualizacion visible en < 500ms
- No hay diferencia perceptible entre pantallas
- El cliente ve el cambio al mismo tiempo que el empleado

## 6. Criterios de Exito

- [ ] Latencia < 500ms
- [ ] Actualizacion fluida
- [ ] Sin errores de conexion

## 7. Trazabilidad

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria|REQ-10 Pantalla Secundaria]] - CA-02
- Change Request: [[05-Control de cambios/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]]
- Plan Maestro: [[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*