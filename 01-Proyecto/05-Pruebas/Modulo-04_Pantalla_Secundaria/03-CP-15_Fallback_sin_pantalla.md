---
id: CP-15
titulo: Fallback cuando no hay pantalla secundaria
modulo: Pantalla_Secundaria
tipo_prueba: Sistema
requerimiento: REQ-10_Pantalla_Secundaria
version_sistema: "1.0"
estado: Pendiente
entrada: Sin pantalla secundaria conectada
precondiciones: Sistema iniciado, NO hay pantalla secundaria
pasos:
  - 1. Iniciar el sistema sin pantalla secundaria
  - 2. Usar la aplicacion normalmente
resultado_esperado: El sistema funciona normalmente en pantalla principal
resultado_actual: ""
paso_fallo: ""
severidad_defecto: ""
fecha_ejecucion: ""
responsable: ""
tags:
  - cp/pendiente
  - modulo/pantalla-secundaria
  - req/pendiente
  - scope-creep
---

# CP-15: Fallback cuando no hay pantalla secundaria

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-15 |
| **Modulo** | Pantalla Secundaria (Modulo-04) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-10_Pantalla_Secundaria]] |
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

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-10_Pantalla_Secundaria]] - CA-03, RN-10-01
- Change Request: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-04_Pantalla_Secundaria]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*