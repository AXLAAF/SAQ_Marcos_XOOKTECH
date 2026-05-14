---
id: REQ-02
titulo: Previsualizacion del Marco sobre la Foto
version: "1.0"
estado: Implementado
prioridad: Alta
tipo: Funcional
modulo: Previsualizacion
fecha_creacion: 2026-03-19
ultima_revision: 2026-03-19
responsable: Samuel Blanco
fuente: Entrevista con cliente, Propuesta recuperada
criterios_aceptacion:
  - CA-01: El sistema superpone el marco seleccionado sobre la foto del cliente
  - CA-02: Las proporciones del marco coinciden con las dimensiones reales
  - CA-03: El renderizado 3D se actualiza en menos de 2 segundos
  - CA-04: El usuario puede cambiar de marco y ver la actualizacion en tiempo real
dependencias:
  - REQ-01_Carga_Imagen
  - REQ-03_Generacion_Marcos_3D
change_requests: []
casos_prueba:
  - CP-08_Marco_simple
  - CP-12_Proporciones
referencias_biblio:
  - SWEBOK v4 KA1 sec 4.5
tags:
  - req/funcional
  - modulo/previsualizacion
  - req/implementado
---

# REQ-02: Previsualizacion del Marco sobre la Foto

## 1. Descripcion General

Una vez que el cliente ha subido su foto y seleccionado un marco del catalogo, el sistema debe mostrar una previsualizacion realista de como quedaria la foto con el marco seleccionado. La previsualizacion debe ser en 3D y actualizarse en tiempo real cuando el usuario cambia de marco.

## 2. Reglas de Negocio

- RN-02-01: El marco debe renderizarse en 3D sobre la fotografia del cliente
- RN-02-02: Las proporciones del marco deben corresponder a las dimensiones reales (ancho x alto)
- RN-02-03: La previsualizacion debe actualizarse en menos de 2 segundos al cambiar de marco
- RN-02-04: El usuario puede superponer varios marcos para comparar

## 3. Precondiciones

- El cliente ha subido una imagen exitosamente (REQ-01 completado)
- El catalogo de marcos esta cargado en el sistema
- El usuario ha seleccionado al menos un marco del catalogo

## 4. Flujo Principal (Happy Path)

1. El cliente selecciona un marco del catalogo
2. El sistema recupera la informacion del marco (textura, dimensiones, modelo 3D)
3. El sistema genera el renderizado 3D del marco sobre la fotografia del cliente
4. El sistema muestra la previsualizacion en el area designada
5. El usuario puede seleccionar un marco diferente
6. El sistema actualiza la previsualizacion automaticamente
7. El proceso se repite hasta que el cliente este satisfecho

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | El usuario cambia rapidamente entre varios marcos | El sistema cancela renderizados pendientes y solo muestra el ultimo |
| FA-02 | El usuario ajusta el tamano de la ventana del navegador | El sistema reajusta la previsualizacion manteniando proporciones |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | La textura del marco no carga correctamente | El sistema muestra el marco con color solido y marca la incidencia |
| FE-02 | El modelo 3D tiene errores de renderizado | El sistema muestra un mensaje de error y ofrece reintentar |
| FE-03 | Rendimiento lento por dispositivo del cliente | El sistema reduce la calidad del renderizado automaticamente |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | El cliente tiene una foto cargada y selecciona un marco | Hace clic en el marco en el catalogo | El sistema muestra la previsualizacion en menos de 2 segundos |
| CA-02 | El cliente selecciona un marco de 30x40 cm | Se muestra la previsualizacion | Las proporciones del marco corresponden exactly a 30x40 cm |
| CA-03 | El cliente cambia de marco rapidamente | Hace clic en diferentes marcos en secuencia | Solo la ultima seleccion se muestra en pantalla |

## 8. Restricciones Tecnicas

- Renderizado: WebGL/Three.js
- Tiempo de actualizacion: < 2 segundos
- Resolucion minima de salida: 800x600 pixeles
- Proporciones: Deben coincidir con las dimensiones reales del marco

## 9. Dependencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]] - La foto del cliente debe estar cargada
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-03_Generacion_Marcos_3D]] - El modelo 3D del marco debe estar disponible

## 10. Trazabilidad

- Casos de Prueba: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-03_Previsualizacion/CP-08_Marco_simple]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-03_Previsualizacion/CP-12_Proporciones]]
- Change Requests: No aplica

---

*Requerimiento creado: 2026-03-19 | Ultima actualizacion: 2026-03-19*
*Referencia: [[01-Propuesta_Recuperada]], [[04-Minuta_Entrevista_Recuperacion]]