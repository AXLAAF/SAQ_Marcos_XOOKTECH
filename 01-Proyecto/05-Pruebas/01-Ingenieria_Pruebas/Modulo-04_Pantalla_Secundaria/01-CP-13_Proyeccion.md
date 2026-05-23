# CP-13: Proyeccion en pantalla secundaria
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-13 |
| **Modulo** | Pantalla Secundaria (Modulo-04) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria|REQ-10 Pantalla Secundaria]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria|REQ-10 Pantalla Secundaria]] - CA-01
- Change Request: [[07-Control/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]]
- Plan Maestro: [[05-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*