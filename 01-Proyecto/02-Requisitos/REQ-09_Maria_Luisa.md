---
id: REQ-09
titulo: Maria Luisa (Marco Decorativo Interno)
version: "1.0"
estado: Pendiente
prioridad: Media
tipo: Funcional
modulo: Previsualizacion
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Samuel Blanco
fuente: Solicitud del cliente (Enmarcame)
criterios_aceptacion:
  - CA-01: El cliente puede seleccionar diferentes tipos de Maria Luisa
  - CA-02: La Maria Luisa se muestra en la previsualizacion rodeando la foto
  - CA-03: El catalogo de Maria Luisas es independiente del catalogo de marcos
  - CA-04: Las Maria Luisas tienen opciones de color y estilo
dependencias:
  - REQ-02_Previsualizacion_Marco
change_requests:
  - CR-03_Maria_Luisa
casos_prueba:
  - CP-11_Maria_Luisa
referencias_biblio:
  - SWEBOK v4 KA1 - Requisitos Funcionales
tags:
  - req/funcional
  - modulo/previsualizacion
  - req/pendiente
  - scope-creep
---

# REQ-09: Maria Luisa (Marco Decorativo Interno)

## 1. Descripcion General

El sistema debe permitir al cliente seleccionar una Maria Luisa (marco decorativo interno que rodea la fotografia). Esta funcionalidad fue solicitada por el cliente despues de la implementacion inicial del sistema (Scope Creep).

> **Nota**: Este requerimiento representa un cambio al alcance original del proyecto. Esta documentado en [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-03_Maria_Luisa]] para control de cambios.

## 2. Reglas de Negocio

- RN-09-01: La Maria Luisa es un marco decorativo interno que rodea la fotografia
- RN-09-02: El catalogo de Maria Luisas es independiente del catalogo de marcos
- RN-09-03: Cada Maria Luisa tiene colores y estilos disponibles
- RN-09-04: La Maria Luisa se renderiza entre la foto y el marco exterior

## 3. Precondiciones

- El sistema tiene la funcionalidad de previsualizacion basica (REQ-02)
- El catalogo de Maria Luisas esta definido en la base de datos
- Se han escaneado las texturas de las Maria Luisas disponibles

## 4. Flujo Principal (Happy Path)

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

## 7. Criterios de Aceptacion (formato BDD)

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

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-02_Previsualizacion_Marco]] - Requerimiento base de previsualizacion
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-03_Maria_Luisa]] - Change Request asociado

## 10. Trazabilidad

- Casos de Prueba: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-03_Previsualizacion/CP-11_Maria_Luisa]]
- Change Requests: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-03_Maria_Luisa]] (Pendiente de aprobacion)

---

*Requerimiento creado: 2026-03-23 | Estado: Pendiente - No aprobado formalmente*
*Referencia: [[02-Acuerdos_Cliente]] - ACU-008*
*Este es un requerimiento de Scope Creep - necesita aprobacion formal del cliente*