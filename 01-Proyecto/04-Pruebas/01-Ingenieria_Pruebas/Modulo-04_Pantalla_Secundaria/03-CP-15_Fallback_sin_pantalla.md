# CP-15: Fallback cuando no hay pantalla secundaria
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-15 |
| **Modulo** | Pantalla Secundaria (Modulo-04) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria|REQ-10 Pantalla Secundaria]] |
| **Estado** | Pendiente (Scope Creep) |

## 2. Descripcion

Verificar que el sistema funciona correctamente cuando NO hay pantalla secundaria conectada (es opcional).

## 3. Criterio de Aceptacion

- CA-03: El sistema funciona correctamente aunque no haya pantalla secundaria

## 4. Pasos de Ejecucion

1. Apagar/desconectar pantalla secundaria
2. Abrir la aplicacion
3. Usar todas las funciones (cargar foto, seleccionar marco, previsualizar)
4. Generar una orden

## 5. Resultado Esperado

- El sistema funciona al 100% en pantalla principal
- No se muestra error de pantalla faltante
- Todas las funcionalidades disponibles
- RN-10-01: La pantalla secundaria es opcional

## 6. Criterios de Exito

- [ ] Sistema funciona sin errores
- [ ] Sin mensajes de pantalla faltante
- [ ] Todas las funciones operativas

## 7. Trazabilidad

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria|REQ-10 Pantalla Secundaria]] - CA-03, RN-10-01
- Change Request: [[05-Revisiones e inspecciones/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]]
- Plan Maestro: [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*