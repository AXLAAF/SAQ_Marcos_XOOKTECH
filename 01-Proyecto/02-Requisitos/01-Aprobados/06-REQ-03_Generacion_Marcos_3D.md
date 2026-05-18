
# REQ-03: Generacion de Marcos 3D desde Texturas Escaneadas

## 1. Descripcion General

El sistema debe poder generar modelos tridimensionales de marcos a partir de imagenes bidimensionales (texturas) escaneadas. Este proceso es fundamental para la previsualizacion realista y debe ser automatico, detectando las dimensiones del marco a partir de las fotos de perfil.

## 2. Reglas de Negocio

- RN-03-01: Las texturas se escanean a alta resolucion (minimo 300 DPI)
- RN-03-02: El programa Python detecta automaticamente el ancho del marco desde la foto de perfil
- RN-03-03: Cada marco debe tener una textura frontal y una foto de perfil para el 3D
- RN-03-04: El proceso de generacion debe completarse en menos de 30 segundos por marco

## 3. Precondiciones

- Las imagenes de los marcos han sido escaneadas y guardadas en el servidor
- El programa Python esta instalado y configurado correctamente
- La base de datos esta accesible para guardar los modelos generados

## 4. Flujo Principal (Happy Path)

1. El operador inicia el programa de procesamiento de marcos
2. El programa escanea la carpeta de imagenes pendientes de procesar
3. Para cada imagen, el programa:
   a. Analiza la foto de perfil para detectar el ancho del marco
   b. Genera el modelo 3D a partir de la textura frontal
   c. Guarda el modelo en la base de datos
   d. Marca la imagen como procesada
4. El proceso completa y genera un reporte de marcos procesados

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | La imagen de perfil no tiene el marco claramente visible | El programa marca el caso para revision manual |
| FA-02 | La textura tiene resolucion baja | El programa genera el modelo con advertencia de calidad |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | Archivo de imagen corrupto | El programa salta el archivo y continua con el siguiente, registra el error |
| FE-02 | Error de conexion a la base de datos | El programa reintenta 3 veces y si falla, detiene el proceso con mensaje de error |
| FE-03 | Memoria insuficiente para procesamiento | El programa reduce la calidad del modelo y procesa en lotes |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | Se tiene una textura frontal y foto de perfil de un marco | Se ejecuta el programa de procesamiento | Se genera un modelo 3D almacenable en la base de datos |
| CA-02 | Se tiene una foto de perfil de un marco de 5 cm de ancho | El programa analiza la imagen | Detecta correctamente el ancho de 5 cm |
| CA-03 | Se procesan 100 marcos en secuencia | Se ejecuta el programa | Todos los modelos se generan en menos de 50 minutos |

## 8. Restricciones Tecnicas

- Lenguaje: Python 3.x
- Librerias: OpenCV, NumPy, Mesh generation
- Formato de salida: GLTF/GLB o similar
- Resolucion minima de textura: 1024x1024 pixeles

## 9. Dependencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-04_Catalogo_Marcos]] - Los marcos deben estar registrados en el catalogo

## 10. Trazabilidad

- Casos de Prueba: Pendientes de definir en PROC-05
- Change Requests: No aplica
