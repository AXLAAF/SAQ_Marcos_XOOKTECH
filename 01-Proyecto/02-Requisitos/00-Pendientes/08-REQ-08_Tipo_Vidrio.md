---
id: REQ-08
titulo: Tipos de Vidrio
version: "1.0"
estado: Pendiente
prioridad: Media
tipo: Funcional
modulo: Previsualizacion
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Líder SQA
fuente: Solicitud del cliente (Enmarcame)
criterios_aceptacion:
  - CA-01: El cliente puede seleccionar tipo de vidrio (normal, antirreflejo, templo)
  - CA-02: La previsualizacion muestra el efecto del tipo de vidrio seleccionado
  - CA-03: El tipo de vidrio se incluye en la orden de compra
  - CA-04: Cada tipo de vidrio tiene un costo adicional asociado
dependencias:
  - REQ-02_Previsualizacion_Marco
change_requests:
  - CR-02_Tipos_Vidrio
casos_prueba:
  - CP-10_Tipo_vidrio
referencias_biblio:
  - SWEBOK v4 KA1 - Requisitos Funcionales
tags:
  - req/funcional
  - modulo/previsualizacion
  - req/pendiente
  - scope-creep
---

# REQ-08: Tipos de Vidrio

## 1. Descripcion General

El sistema debe permitir al cliente seleccionar el tipo de vidrio para su marco. Esta funcionalidad fue solicitada por el cliente despues de la implementacion inicial del sistema (Scope Creep).

> **Nota**: Este requerimiento representa un cambio al alcance original del proyecto. Esta documentado en [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-02_Tipos_Vidrio]] para control de cambios.

## 2. Reglas de Negocio

- RN-08-01: Los tipos de vidrio disponibles son: Normal, Antirreflejo, Templo (cristal templado)
- RN-08-02: Cada tipo de vidrio tiene un precio adicional
- RN-08-03: El efecto visual del vidrio debe ser visible en la previsualizacion
- RN-08-04: El tipo de vidrio seleccionado debe guardarse en la orden

## 3. Precondiciones

- El sistema tiene la funcionalidad de previsualizacion basica (REQ-02)
- Los tipos de vidrio y sus precios estan definidos en la base de datos

## 4. Flujo Principal (Happy Path)

1. El cliente selecciona un marco y carga su foto
2. El sistema muestra la previsualizacion del marco
3. El cliente hace clic en "Tipo de Vidrio"
4. El sistema muestra las opciones disponibles (Normal, Antirreflejo, Templo)
5. El cliente selecciona el tipo de vidrio deseado
6. La previsualizacion se actualiza para mostrar el efecto del vidrio
7. El precio total se actualiza con el costo adicional del vidrio

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | El cliente no selecciona ningun tipo de vidrio | Se asume el tipo "Normal" por defecto |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | El tipo de vidrio no esta disponible para el marco | Se muestra un mensaje indicando la incompatibilidad |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | El cliente abre la opcion de tipo de vidrio | Ve el menu desplegable | Se muestran las 3 opciones con sus precios |
| CA-02 | El cliente selecciona "Vidrio Antirreflejo" | Se aplica la seleccion | La previsualizacion muestra el efecto de reduccion de brillo |
| CA-03 | El cliente genera la orden con vidrio | Se completa la orden | El tipo de vidrio aparece en los detalles de la orden |

## 8. Restricciones Tecnicas

- Tipos de vidrio definidos en base de datos
- Efectos visuales mediante shaders o texturas
- Precio adicional por tipo almacenado en BD

## 9. Dependencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-02_Previsualizacion_Marco]] - Requerimiento base de previsualizacion
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-02_Tipos_Vidrio]] - Change Request asociado

## 10. Trazabilidad

- Casos de Prueba: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-03_Previsualizacion/CP-10_Tipo_vidrio]]
- Change Requests: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-02_Tipos_Vidrio]] (Pendiente de aprobacion)

---

*Requerimiento creado: 2026-03-23 | Estado: Pendiente - No aprobado formalmente*
*Referencia: [[02-Acuerdos_Cliente]] - ACU-007*
*Este es un requerimiento de Scope Creep - necesita aprobacion formal del cliente*