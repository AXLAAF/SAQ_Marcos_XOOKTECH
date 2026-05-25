
# REQ-09: Maria Luisa o Marco Decorativo Interno
**Responsable:** Analista de Requerimientos
**Entradas:** Línea Base y Especificaciones Iniciales
**Salidas:** Matriz de Trazabilidad e Requisitos Formales

---

## 1. Descripcion General

El sistema debe permitir al cliente seleccionar una Maria Luisa (marco decorativo interno que rodea la fotografia). Esta funcionalidad fue solicitada por el cliente despues de la implementacion inicial del sistema (Scope Creep).

> **Nota**: Este requerimiento representa un cambio al alcance original del proyecto. Esta documentado en [[05-Revisiones e inspecciones/01-Ingenieria_Control/10-CR-03_Maria_Luisa|CR-03 María Luisa]] para control de cambios.

## 2. Reglas de Negocio

- RN-09-01: La Maria Luisa es un marco decorativo interno que rodea la fotografia
- RN-09-02: El catalogo de Maria Luisas es independiente del catalogo de marcos
- RN-09-03: Cada Maria Luisa tiene colores y estilos disponibles
- RN-09-04: La Maria Luisa se renderiza entre la foto y el marco exterior

## 3. Precondiciones

- El sistema tiene la funcionalidad de previsualizacion basica (REQ-02)
- El catalogo de Maria Luisas esta definido en la base de datos
- Se han escaneado las texturas de las Maria Luisas disponibles

## 4. Flujo Principal

1. El cliente selecciona un marco y carga su foto
2. El cliente hace clic en "Agregar Maria Luisa"
3. El sistema muestra el catalogo de Maria Luisas disponibles
4. El cliente selecciona una Maria Luisa
5. El cliente selecciona el color de la Maria Luisa
6. La previsualizacion se actualiza mostrando la Maria Luisa rodeando la foto
7. El cliente puede cambiar la Maria Luisa las veces que quiera

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | El cliente no selecciona Maria Luisa | El sistema continua sin Maria Luisa (comportamiento original) |
| FA-02 | La Maria Luisa seleccionada no tiene el color elegido | El sistema muestra un mensaje y sugiere colores disponibles |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | La Maria Luisa no es compatible con el marco seleccionado | Se muestra un mensaje de incompatibilidad |

## 7. Criterios de Aceptacion en formato BDD

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | El cliente abre el menu de Maria Luisa | Ve el catalogo | Se muestran las Maria Luisas disponibles con imagen y nombre |
| CA-02 | El cliente selecciona una Maria Luisa | Se aplica la seleccion | La previsualizacion muestra la Maria Luisa rodeando la foto |
| CA-03 | El cliente cambia el color de la Maria Luisa | Se selecciona un nuevo color | La previsualizacion se actualiza con el nuevo color |

## 8. Restricciones Tecnicas

- Maria Luisas almacenadas en base de datos separada
- Renderizado en orden: foto -> Maria Luisa -> marco
- Soporte para multiples estilos y colores por Maria Luisa

## 9. Dependencias

- [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02 Previsualización Marco]] - Requerimiento base de previsualizacion
- [[05-Revisiones e inspecciones/01-Ingenieria_Control/10-CR-03_Maria_Luisa|CR-03 María Luisa]] - Change Request asociado

## 10. Trazabilidad

- Casos de Prueba: [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/04-CP-11_Maria_Luisa]]
- Change Requests: [[05-Revisiones e inspecciones/01-Ingenieria_Control/10-CR-03_Maria_Luisa|CR-03 María Luisa]] (Pendiente de aprobacion)