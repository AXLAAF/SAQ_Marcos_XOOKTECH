# CP-06: Filtro por color de marco
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-06 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05 Filtrado Catálogo]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05 Filtrado Catálogo]] - RN-05-02
- Plan Maestro: [[05-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*