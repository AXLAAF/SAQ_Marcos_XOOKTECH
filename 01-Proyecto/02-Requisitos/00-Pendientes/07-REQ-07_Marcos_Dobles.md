
# REQ-07: Marcos Dobles

## 1. Descripcion General

El sistema debe permitir la previsualizacion de marcos dobles, es decir, marcos que contienen dos fotografias. Esta funcionalidad fue solicitada por el cliente despues de la implementacion inicial del sistema (Scope Creep).

> **Nota**: Este requerimiento representa un cambio al alcance original del proyecto. Esta documentado en [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-01_Marcos_Dobles]] para control de cambios.

## 2. Reglas de Negocio

- RN-07-01: Los marcos dobles tienen dos espacios para fotografias
- RN-07-02: Cada espacio de foto puede tener un tamano independiente
- RN-07-03: No todos los marcos suportan la modalidad doble (solo algunos)
- RN-07-04: La distancia entre los dos espacios es configurable

## 3. Precondiciones

- El sistema tiene la funcionalidad de previsualizacion basica (REQ-02)
- Los marcos que soportan modo doble estan marcados en la base de datos

## 4. Flujo Principal (Happy Path)

1. El cliente selecciona un marco del catalogo
2. El sistema verifica si el marco soporta modo doble
3. Si soporta modo doble, el cliente puede activar la opcion "Marco Doble"
4. El cliente carga la primera foto
5. El cliente carga la segunda foto
6. El sistema muestra la previsualizacion con ambas fotos en el marco
7. El cliente puede ajustar el tamano de cada espacio

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | El cliente selecciona un marco que no soporta modo doble | La opcion "Marco Doble" aparece deshabilitada |
| FA-02 | Solo se carga una foto en modo doble | El sistema muestra un espacio vacio con la opcion de agregar |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | Las fotos exceden el tamano maximo permitido | El sistema comprime automaticamente las imagenes |
| FE-02 | El marco seleccionado no tiene soporte para modo doble | Se muestra mensaje de error y se sugiere otro marco |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | El cliente selecciona un marco que soporta modo doble | Activa la opcion "Marco Doble" | El sistema muestra dos espacios para fotos |
| CA-02 | El cliente carga dos fotos en un marco doble | Se completa la carga | La previsualizacion muestra ambas fotos en el marco |
| CA-03 | El cliente ajusta el tamano de un espacio de foto | Modifica el tamano | El otro espacio se ajusta automaticamente para mantener proporciones |

## 8. Restricciones Tecnicas

- Tamano maximo por imagen: 5 MB
- Formatos soportados: JPG, PNG
- Renderizado 3D requiere modelos especiales para modo doble

## 9. Dependencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-02_Previsualizacion_Marco]] - Requerimiento base de previsualizacion
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-01_Marcos_Dobles]] - Change Request asociado

## 10. Trazabilidad

- Casos de Prueba: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-03_Previsualizacion/CP-09_Marco_doble]]
- Change Requests: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-01_Marcos_Dobles]] (Pendiente de aprobacion)
