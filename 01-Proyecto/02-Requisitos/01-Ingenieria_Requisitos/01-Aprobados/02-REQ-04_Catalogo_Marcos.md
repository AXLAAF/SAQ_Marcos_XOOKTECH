

# REQ-04: Catalogo de Marcos
**Responsable:** Analista de Requerimientos
**Entradas:** Línea Base y Especificaciones Iniciales
**Salidas:** Matriz de Trazabilidad e Requisitos Formales

---

## 1. Descripcion General

El sistema debe proporcionar un catalogo completo de marcos disponibles para que los clientes puedan explorar y seleccionar el marco deseado. El catalogo debe ser facil de navegar y proporcionar informacion relevante de cada marco.

## 2. Reglas de Negocio

- RN-04-01: El catalogo debe incluir todos los marcos del inventario de Enmarcame
- RN-04-02: Cada marco debe mostrar: imagen, clave, nombre, categoria, precio
- RN-04-03: El catalogo debe ser paginado o cargar de forma infinita
- RN-04-04: Los filtros deben combinarse entre si (AND logico)

## 3. Precondiciones

- La base de datos tiene los marcos cargados
- Las imagenes de los marcos estan disponibles en el servidor
- La aplicacion web esta funcionando correctamente

## 4. Flujo Principal

1. El cliente accede a la seccion de catalogo de la aplicacion
2. El sistema carga y muestra los marcos disponibles en formato de grilla
3. El cliente puede navegar por las paginas del catalogo
4. El cliente puede aplicar filtros para buscar marcos especificos
5. El cliente hace clic en un marco para ver los detalles
6. El sistema muestra la informacion completa del marco

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | El cliente busca un marco por nombre | El sistema filtra y muestra los resultados coincidentes |
| FA-02 | El cliente aplica multiples filtros | El sistema combina los filtros y muestra resultados |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | La base de datos no responde | El sistema muestra mensaje de error y ofrece reintentar |
| FE-02 | Una imagen de marco no esta disponible | El sistema muestra una imagen placeholder |

## 7. Criterios de Aceptacion en formato BDD

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | El cliente abre el catalogo | Accede a la seccion de catalogo | Se cargan y muestran todos los marcos en menos de 3 segundos |
| CA-02 | El cliente tiene 1079 marcos en el catalogo | Navega por las paginas | El rendimiento no se degrada significativamente |
| CA-03 | El cliente filtra por color "Dorado" | Aplica el filtro | Se muestran solo los marcos de color dorado |

## 8. Restricciones Tecnicas

- Base de datos: PostgreSQL
- Formato de imagenes: JPG, PNG
- Tamano maximo de imagen: 500 KB
- Paginacion: 50 marcos por pagina

## 9. Dependencias

- Ninguna dependencia critica

## 10. Trazabilidad

- Casos de Prueba: [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/01-CP-04_Carga_catalogo]], [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/02-CP-05_Filtro_modelo]], [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/03-CP-06_Filtro_color]], [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/04-CP-07_Filtro_ancho]]
- Change Requests: No aplica