# CP-04: Carga completa del catalogo de marcos
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-04 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos|REQ-04 Catálogo de Marcos]], [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/04-REQ-06_Datos_Catalogo|REQ-06 Datos Catálogo]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el catalogo de marcos se carga completamente y muestra todos los registros disponibles en la base de datos.

## 3. Criterios de Aceptacion

- CA-04-01: El sistema muestra el catalogo al iniciar
- CA-04-02: Se cargan todos los marcos disponibles

## 4. Pasos de Ejecucion

1. Abrir la aplicacion web
2. Navegar a la seccion "Catalogo"
3. Observar la carga del catalogo
4. Contar el numero de marcos mostrados

## 5. Resultado Esperado

- Se cargan aproximadamente 1,079 marcos
- El grid de marcos se visualiza correctamente
- Cada marco muestra: imagen, nombre, precio
- El tiempo de carga es aceptable (< 5 segundos)

## 6. Criterios de Exito

- [ ] El catalogo carga todos los marcos
- [ ] No hay errores de conexion
- [ ] La interfaz es responsive

## 7. Trazabilidad

- Requerimientos: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos|REQ-04 Catálogo de Marcos]], [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/04-REQ-06_Datos_Catalogo|REQ-06 Datos Catálogo]]
- Plan Maestro: [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*