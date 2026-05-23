# Manual de Terminologia Tecnica del Proyecto

> **Directiva de Lenguaje**: El equipo debe utilizar exclusivamente los terminos definidos en este glosario para la redaccion de todos los artefactos (`REQ`, `DIS`, `COD`, `CP`, etc.). El uso de lenguaje coloquial o ambiguo invalidara la profundidad tecnica del documento.

---

## 1. Terminologia de Aseguramiento de Calidad (SQA)

1.  **ETVX (Entry, Task, Validation, Exit)**: Modelo mandatorio para la estructura de procesos. Cada archivo `00-PROC` debe demostrar el cumplimiento de estas cuatro etapas.
2.  **Linea Base (Baseline)**: Especificacion aprobada y congelada que sirve como punto de partida para cambios controlados. En este proyecto, cada fase (01-08) genera una linea base al pasar a `#estado/verificado`.
3.  **SCM (Software Configuration Management)**: Disciplina aplicada en la carpeta `07-Control` para identificar, organizar y controlar las modificaciones al software y su documentacion.
4.  **V&V (Verificacion y Validacion)**: 
    - **Verificacion**: ¿Estamos construyendo el producto correctamente? (Revision de documentos).
    - **Validacion**: ¿Estamos construyendo el producto correcto? (Ejecucion de pruebas sobre el prototipo).

## 2. Terminologia de Gestion y Control

1.  **Matriz de Trazabilidad (RTM)**: Documento central en `07-Control` que garantiza que cada requerimiento tenga un diseño, un codigo y una prueba asociada.
2.  **Densidad de Defectos**: Metrica mandatoria calculada como `Total de errores / Complejidad del modulo`. Debe registrarse en el Dashboard de Calidad.
3.  **Inspeccion Formal**: Revision tecnica siguiendo el metodo de Galin (uso de checklists y roles definidos) para detectar defectos antes de la fase de pruebas.

## 3. Terminologia del Prototipo (Realidad Tecnica)

1.  **Deteccion de Aristas (Canny/OpenCV)**: Algoritmo real usado en el modulo de vision para identificar el ancho de la moldura del marco.
2.  **Renderizado por Capas (Pillow)**: Tecnica de superposicion de imagenes para visualizar el marco doble y la Maria Luisa sobre la foto del cliente.
3.  **Despliegue (Deployment)**: Proceso de transferencia del codigo desde el entorno de desarrollo al entorno de ejecucion final de "Enmarcame".
4.  **Mantenimiento Correctivo**: Actividades de soporte destinadas a eliminar defectos detectados por el usuario final tras el despliegue.

---
*Ultima actualizacion: 2026-05-12 | Analista Técnico (SQA Lead)*