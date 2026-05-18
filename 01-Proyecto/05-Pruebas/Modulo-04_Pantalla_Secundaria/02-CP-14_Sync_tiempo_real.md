# CP-14: Sincronizacion en tiempo real entre pantallas

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-14 |
| **Modulo** | Pantalla Secundaria (Modulo-04) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-10_Pantalla_Secundaria]] |
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

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-10_Pantalla_Secundaria]] - CA-02
- Change Request: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-04_Pantalla_Secundaria]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01-Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*
