---
id: CP-06
titulo: Filtro por color de marco
modulo: Catalogo
tipo_prueba: Sistema
requerimiento: REQ-05_Filtrado_Catalogo
version_sistema: "1.0"
estado: Pendiente
entrada: Seleccion de color "Negro"
precondiciones: Catalogo cargado completamente
pasos:
  - 1. Acceder a la seccion Catalogo
  - 2. Seleccionar filtro de color "Negro"
  - 3. Observar resultados filtrados
resultado_esperado: Solo se muestran marcos de color Negro
resultado_actual: ""
paso_fallo: ""
severidad_defecto: ""
fecha_ejecucion: ""
responsable: ""
tags:
  - cp/pendiente
  - modulo/catalogo
  - req/funcional
---

# CP-06: Filtro por color de marco

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-06 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-05_Filtrado_Catalogo]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el filtro por color muestra solo los marcos del color seleccionado.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Filtro seleccionado | Color: "Negro" |
| Valor esperado | Marcos con color = Negro |

## 4. Pasos de Ejecucion

1. Acceder al catalogo
2. Seleccionar "Negro" en filtro de color
3. Observar resultados

## 5. Resultado Esperado

- Se muestran solo marcos de color Negro
- El contador de resultados se actualiza
- Los demas filtros siguen disponibles

## 6. Criterios de Exito

- [ ] Filtro muestra resultados correctos
- [ ] Sin errores en consola

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-05_Filtrado_Catalogo]] - RN-05-02
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*