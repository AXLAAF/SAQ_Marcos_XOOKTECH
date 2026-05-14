---
id: CP-05
titulo: Filtro por modelo/categoria de marco
modulo: Catalogo
tipo_prueba: Sistema
requerimiento: REQ-05_Filtrado_Catalogo
version_sistema: "1.0"
estado: Pendiente
entrada: Seleccion de categoria "Clasico"
precondiciones: Catalogo cargado completamente
pasos:
  - 1. Acceder a la seccion Catalogo
  - 2. Seleccionar filtro de categoria "Clasico"
  - 3. Observar resultados filtrados
resultado_esperado: Solo se muestran marcos de categoria Clasico
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

# CP-05: Filtro por modelo/categoria de marco

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-05 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-05_Filtrado_Catalogo]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el filtro por categoria/modelo funciona correctamente y muestra solo los marcos que coinciden.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Filtro seleccionado | Categoria: "Clasico" |
| Valor esperado | Marcos con categoria = Clasico |

## 4. Pasos de Ejecucion

1. Acceder al catalogo
2. Localizar dropdown de filtros
3. Seleccionar "Clasico" en categoria
4. Observar los resultados

## 5. Resultado Esperado

- Se muestran solo marcos de categoria "Clasico"
- El contador de resultados se actualiza
- Los otros filtros permanecen disponibles

## 6. Criterios de Exito

- [ ] Filtro funciona correctamente
- [ ] Resultados son relevantes
- [ ] UI se actualiza sin errores

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-05_Filtrado_Catalogo]] - RN-05-01
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*