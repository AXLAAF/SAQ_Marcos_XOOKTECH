# CP-05: Filtro por modelo/categoria de marco
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-05 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05 Filtrado Catálogo]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05 Filtrado Catálogo]] - RN-05-01
- Plan Maestro: [[05-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*