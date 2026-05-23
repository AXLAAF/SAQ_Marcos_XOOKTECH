# CP-07: Filtro por ancho de marco
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-07 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05 Filtrado Catálogo]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el filtro por rango de ancho muestra solo los marcos cuyas dimensiones estan dentro del rango especificado.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Filtro seleccionado | Ancho: 30-50 cm |
| Valor esperado | Marcos con 30cm <= ancho <= 50cm |

## 4. Pasos de Ejecucion

1. Acceder al catalogo
2. Localizar campo de filtro de ancho
3. Ingresar valor minimo: 30
4. Ingresar valor maximo: 50
5. Observar resultados

## 5. Resultado Esperado

- Se muestran solo marcos con ancho entre 30 y 50 cm
- El contador de resultados se actualiza
- La seleccion es inclusiva (incluye valores limite)

## 6. Criterios de Exito

- [ ] Filtro incluye marcos de 30cm
- [ ] Filtro incluye marcos de 50cm
- [ ] Excluye marcos menores a 30cm y mayores a 50cm

## 7. Trazabilidad

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05 Filtrado Catálogo]] - RN-05-03
- Plan Maestro: [[05-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*