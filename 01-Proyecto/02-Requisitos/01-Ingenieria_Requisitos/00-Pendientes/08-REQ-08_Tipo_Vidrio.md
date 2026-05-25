
# REQ-08: Tipos de Vidrio
**Responsable:** Analista de Requerimientos
**Entradas:** Línea Base y Especificaciones Iniciales
**Salidas:** Matriz de Trazabilidad e Requisitos Formales

---

## 1. Descripcion General

El sistema debe permitir al cliente seleccionar el tipo de vidrio para su marco. Esta funcionalidad fue solicitada por el cliente despues de la implementacion inicial del sistema (Scope Creep).

> **Nota**: Este requerimiento representa un cambio al alcance original del proyecto. Esta documentado en [[05-Control de cambios/01-Ingenieria_Control/09-CR-02_Tipos_Vidrio|CR-02 Tipos de Vidrio]] para control de cambios.

## 2. Reglas de Negocio

- RN-08-01: Los tipos de vidrio disponibles son: Normal, Antirreflejo, Templo (cristal templado)
- RN-08-02: Cada tipo de vidrio tiene un precio adicional
- RN-08-03: El efecto visual del vidrio debe ser visible en la previsualizacion
- RN-08-04: El tipo de vidrio seleccionado debe guardarse en la orden

## 3. Precondiciones

- El sistema tiene la funcionalidad de previsualizacion basica (REQ-02)
- Los tipos de vidrio y sus precios estan definidos en la base de datos

## 4. Flujo Principal

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

## 7. Criterios de Aceptacion en formato BDD

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

- [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02 Previsualización Marco]] - Requerimiento base de previsualizacion
- [[05-Control de cambios/01-Ingenieria_Control/09-CR-02_Tipos_Vidrio|CR-02 Tipos de Vidrio]] - Change Request asociado

## 10. Trazabilidad

- Casos de Prueba: [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/03-CP-10_Tipo_vidrio]]
- Change Requests: [[05-Control de cambios/01-Ingenieria_Control/09-CR-02_Tipos_Vidrio|CR-02 Tipos de Vidrio]] (Pendiente de aprobacion)