
# REQ-05: Filtrado del Catalogo
**Responsable:** Analista de Requerimientos
**Entradas:** Línea Base y Especificaciones Iniciales
**Salidas:** Matriz de Trazabilidad e Requisitos Formales

---

## 1. Descripcion General

El sistema debe proporcionar opciones de filtrado para que los clientes puedan encontrar rapidamente los marcos que buscan. Los filtros deben ser intuitivos y proporcionarle al cliente un control efectivo sobre la seleccion.

## 2. Reglas de Negocio

- RN-05-01: Los filtros disponibles son: categoria, color, ancho (rango), estilo
- RN-05-02: Los filtros se combinan con logica AND
- RN-05-03: El filtro debe actualizar los resultados en tiempo real
- RN-05-04: Se debe mostrar la cantidad de resultados despues de aplicar filtros

## 3. Precondiciones

- El catalogo de marcos esta cargado
- Las categorias, colores y anchos estan definidos en la base de datos

## 4. Flujo Principal (Happy Path)

1. El cliente esta en la pagina del catalogo
2. El cliente hace clic en el panel de filtros
3. El cliente selecciona una categoria (ej. Moderno)
4. El sistema filtra instantaneamente y muestra los resultados
5. El cliente selecciona un color (ej. Dorado)
6. El sistema combina los filtros y muestra marcos modernos de color dorado

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | El cliente no selecciona ningun filtro | El sistema muestra todos los marcos |
| FA-02 | Los filtros no encontraron resultados | El sistema muestra mensaje "No se encontraron resultados" |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | Error en la consulta de filtros | El sistema muestra error y mantiene los filtros anteriores |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | El cliente selecciona filtro "Color: Dorado" | Aplica el filtro | Se muestran solo los marcos de color dorado |
| CA-02 | El cliente selecciona filtros "Color: Dorado" y "Categoria: Clasico" | Aplica ambos filtros | Se muestran marcos clasicos de color dorado |
| CA-03 | El cliente aplica un filtro que no tiene resultados | Se aplica el filtro | Se muestra mensaje de "sin resultados" y boton para limpiar filtros |

## 8. Restricciones Tecnicas

- Filtros consultables via API del backend
- Respuesta maxima de 1 segundo para actualizacion de filtros

## 9. Dependencias

- [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos|REQ-04 Catálogo de Marcos]] - Requerimiento base del catalogo

## 10. Trazabilidad

- Casos de Prueba: [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/02-CP-05_Filtro_modelo]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/03-CP-06_Filtro_color]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/04-CP-07_Filtro_ancho]]

- Change Requests: No aplica