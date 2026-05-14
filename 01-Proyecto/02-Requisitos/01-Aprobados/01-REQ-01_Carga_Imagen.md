---
id: REQ-01
titulo: Carga de Imagen del Cliente
version: "1.0"
estado: Implementado
prioridad: Alta
tipo: Funcional
modulo: Carga
fecha_creacion: 2026-03-19
ultima_revision: 2026-03-19
responsable: Analista Técnico
fuente: Entrevista con cliente, Propuesta recuperada
criterios_aceptacion:
  - CA-01: El sistema acepta imagenes en formato JPG hasta 10 MB
  - CA-02: El sistema acepta imagenes en formato PNG hasta 10 MB
  - CA-03: El sistema rechaza archivos que no sean imagenes con mensaje claro
  - CA-04: El sistema comprime imagenes mayores a 5 MB para optimizar rendimiento
dependencias: []
change_requests: []
casos_prueba:
  - CP-01_JPG_valida
  - CP-02_Archivo_invalido
  - CP-03_Imagen_grande
referencias_biblio:
  - SWEBOK v4 KA1 sec 4.5
tags:
  - req/funcional
  - modulo/carga
  - req/implementado
---
# REQ-01: Carga de Imagen del Cliente

## 1. Descripcion General

El cliente debe poder subir una fotografia desde la aplicacion web para usarla como base de la previsualizacion. El sistema acepta imagenes en formatos comunes (JPG, PNG) y maneja casos de error de manera clara.

## 2. Reglas de Negocio

- RN-01-01: El archivo debe ser una imagen en formato JPG o PNG
- RN-01-02: El tamano maximo del archivo es 10 MB
- RN-01-03: El sistema comprime automaticamente imagenes mayores a 5 MB
- RN-01-04: La imagen debe tener dimensiones minimas de 200x200 pixeles

## 3. Precondiciones

- El navegador del cliente esta en la pagina principal de la aplicacion
- El sistema esta conectado a la base de datos y funcionando
- No hay restricciones de red que impidan la subida de archivos

## 4. Flujo Principal (Happy Path)

1. El cliente hace clic en el boton "Subir mi foto"
2. El sistema abre el dialogo de seleccion de archivos del sistema operativo
3. El cliente selecciona una imagen de su dispositivo
4. El sistema valida el formato (JPG/PNG) y tamano (max 10 MB)
5. Si la imagen es mayor a 5 MB, el sistema la comprime automaticamente
6. El sistema muestra la imagen en el area de previsualizacion
7. El proceso concluye exitosamente

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora                            | Respuesta del Sistema                                      |
| ----- | ------------------------------------------------ | ---------------------------------------------------------- |
| FA-01 | El cliente cancela la seleccion de archivo       | El sistema cierra el dialogo sin cambios                   |
| FA-02 | El cliente selecciona un archivo de mas de 10 MB | El sistema muestra mensaje de error y no acepta el archivo |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error                          | Respuesta del Sistema                                                |
| ----- | ------------------------------------------- | -------------------------------------------------------------------- |
| FE-01 | Conexion de red se pierde durante la subida | El sistema muestra mensaje de error y permite reintentar             |
| FE-02 | Archivo corrupto que no se puede leer       | El sistema muestra mensaje de error indicando formato no valido      |
| FE-03 | Error interno del servidor                  | El sistema muestra mensaje de error generico y registra el incidente |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado                                           | Cuando                      | Entonces                                                                   |
| ----- | ---------------------------------------------- | --------------------------- | -------------------------------------------------------------------------- |
| CA-01 | El cliente tiene un archivo JPG valido de 5 MB | Lo selecciona en el dialogo | El sistema acepta y muestra la imagen sin compresion                       |
| CA-02 | El cliente intenta subir un archivo PDF        | Lo selecciona en el dialogo | El sistema muestra mensaje de error "Formato no valido"                    |
| CA-03 | El cliente intenta subir una imagen de 15 MB   | Lo selecciona en el dialogo | El sistema muestra mensaje de error "El archivo excede el limite de 10 MB" |

## 8. Restricciones Tecnicas

- Formato de datos: JPG, PNG
- Tamano maximo: 10 MB
- Dimensiones minimas: 200x200 pixeles
- Rendimiento: La carga debe completarse en menos de 3 segundos para archivos menores a 5 MB

## 9. Dependencias

- Ninguna dependencia critica con otros modulos

## 10. Trazabilidad

- Casos de Prueba: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-01_Carga/CP-01_JPG_valida]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-01_Carga/CP-02_Archivo_invalido]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/Modulo-01_Carga/CP-03_Imagen_grande]]
- Change Requests: No aplica

---

*Requerimiento creado: 2026-03-19 | Ultima actualizacion: 2026-03-19*
*Referencia: [[01-Propuesta_Recuperada]], [[02-Acuerdos_Cliente]]
