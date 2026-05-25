# REQ-01: Carga de Imagen del Cliente
**Responsable:** Analista de Requerimientos
**Entradas:** Línea Base y Especificaciones Iniciales
**Salidas:** Matriz de Trazabilidad e Requisitos Formales

---

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

## 4. Flujo Principal

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

## 7. Criterios de Aceptacion en formato BDD

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

- Casos de Prueba: [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/01-CP-01_JPG_valida]], [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/02-CP-02_Archivo_invalido]], [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/03-CP-03_Imagen_grande]]
- Change Requests: No aplica
  