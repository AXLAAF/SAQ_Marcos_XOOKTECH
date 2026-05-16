---
id: PROC-03
titulo: Proceso 3 - Documentación de la Arquitectura (Ingeniería Inversa)
version: "4.0"
estado: Activo
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-14
responsable: Analista Técnico
equipo:
  - Analista Técnico (Estrategia y Verificacion)
  - Líder SQA (Implementacion y Operaciones)
  - Analista SQA (Analisis y Control de Calidad)
autor: Analista Técnico / Líder SQA
disparador: Código existente en GitHub y necesidad de trazabilidad técnica.
criterio_entrada: Repositorio funcional (https://github.com/Bigsami89/Marcos2) y REQs validados.
criterio_salida: Línea base de arquitectura (STD-04 a STD-07) sincronizada con el código.
entradas:
  - [[04-Codificacion/00-PROC-04_Codificacion]] (Estado Real del Código)
  - Repositorio GitHub: https://github.com/Bigsami89/Marcos2
salidas:
  - [[03-Diseño/01-STD-04_Diagrama_Componentes]]
  - [[03-Diseño/02-STD-05_Flujo_Sistema]]
  - [[03-Diseño/03-STD-06_Modelo_Datos]]
  - [[03-Diseño/04-STD-07_Arquitectura_Python]]
referencias_biblio:
  - "SWEBOK v4 KA2 - Diseño de Software"
  - "Galin (2004) - Infraestructura de SQA"
tags:
  - meta/proceso
  - fase/diseño
  - tipo/proceso
  - estado/activo
---
# Proceso 3 — Documentación de la Arquitectura

> Como se evidencia en el **PROC-04 (NT-2)**, este proyecto inició su fase de desarrollo sin una etapa de diseño previa. El código en el repositorio [Marcos2](https://github.com/Bigsami89/Marcos2) es la actual. Este proceso define cómo extraer  para formalizar la arquitectura y asegurar que el mantenimiento.

## 1. Estructura del Proceso (Modelo ETVX)

| Fase                       | Definición          | Detalles                                                                     |
| :------------------------- | :------------------- | :--------------------------------------------------------------------------- |
| **[E] Entry**        | Criterios de Entrada | Acceso al repositorio GitHub + REQs en estado `Aprobado`.                  |
| **[T] Tasks**        | Tareas Operativas    | Ejecutar los 5 pasos de Ingeniería Inversa detallados abajo.                |
| **[V] Verification** | Calidad del Diseño  | El Líder SQA realiza un "Walkthrough" comparando diagramas vs código real. |
| **[X] Exit**         | Criterios de Salida  | Artefactos STD firmados y Matriz de Trazabilidad DIS-REQ actualizada.        |

## 2. Metodología Detallada de Ingeniería Inversa

Para recuperar el diseño a partir de lo implementado por el Líder SQA, se deben ejecutar las siguientes actividades específicas:

### 2.1 Revisiòn de Estructura de Archivos y Capas

- **Actividad**: Mapear la jerarquía de carpetas del repositorio para identificar el patrón de diseño real, actualmente una mezcla de Scripting y Capas.
- **Especificación**: Identificar dónde reside la lógica de **Flask** (rutas), dónde la de **OpenCV** (servicios de visión) y dónde la de **Pillow** (renderizado).
- **Artefacto Destino**: Base del [[01-STD-04_Diagrama_Componentes]].

### 2.2 Análisis de Flujo de Datos y Peticiones (Request Lifecycle)

- **Actividad**: Rastrear una petición HTTP desde el frontend hasta la respuesta final.
- **Especificación**: Documentar qué pasa exactamente cuando se llama a `/upload`. ¿Quién procesa la imagen? ¿Cómo se pasan las coordenadas de OpenCV a la capa de renderizado?
- **Artefacto Destino**: [[02-STD-05_Flujo_Sistema]] (usando diagramas de secuencia Mermaid).

### 2.3 Modelado de Datos Post-Implementación

- **Actividad**: Analizar las clases de Python y las estructuras de datos (diccionarios, listas, DB) que el Líder SQA usa para manejar los marcos y pedidos.
- **Especificación**: Definir atributos reales como `Ancho_Real`, `Textura_Path`, y las relaciones entre el catálogo de marcos y la imagen del usuario.
- **Artefacto Destino**: [[03-STD-06_Modelo_Datos]].

### 2.4 Documentación de la API (Flask Endpoints)

- **Actividad**: Listar todas las rutas decoradas con `@app.route` en el código principal.
- **Especificación**: Para cada ruta, documentar el método (GET/POST), los parámetros de entrada y el formato de respuesta (JSON/Imagen).
- **Artefacto Destino**: [[04-STD-07_Arquitectura_Python]].

### 2.5 Validación de Artefactos Existentes

- **Situación**: Los artefactos actuales en la carpeta `03-Diseño` (STD-04, 05, 06) se consideran **Borradores Técnicos**.
- **Acción**: Deben ser "Refactorizados por Evidencia". Si el diagrama no coincide con el código en GitHub, el diagrama **DEBE** cambiarse para reflejar el código. El diseño sigue al código en esta fase de recuperación.

## 3. Notas Técnicas de Propuesta (NT)

**NT-1: Sincronización mediante Mermaid.js**
Se propone que todos los diagramas de arquitectura se escriban en código Mermaid dentro de Obsidian. Esto facilita que el Analista Técnico pueda actualizarlos rápidamente conforme el Líder SQA realice commits en GitHub.

**NT-2: Creación de un Diccionario de Datos Técnico**
Dado que no se hizo diseño, hay términos en el código que pueden ser ambiguos. Se propone crear una sección en el [[03-STD-06_Modelo_Datos]] que traduzca las variables del código a términos del negocio (Glosario Técnico).

**NT-3: Auditoría de "Dead Code"**
Durante la ingeniería inversa, se deben identificar funciones en el repositorio que ya no se usen (código muerto) para limpiar la arquitectura y evitar documentar componentes obsoletos.

## 4. Recuperacòn 

| Artefacto Generado                 | GitHub                                   | Estado              |
| :--------------------------------- | :--------------------------------------- | :------------------ |
| [[01-STD-04_Diagrama_Componentes]] | `app.py` y estructura de carpetas      | En Refactorización |
| [[02-STD-05_Flujo_Sistema]]        | Lógica de procesamiento en `/process` | En Refactorización |
| [[03-STD-06_Modelo_Datos]]         | Estructuras de datos de Marcos y Pedidos | Pendiente           |

---

*Repositorio Oficial: [Marcos2](https://github.com/Bigsami89/Marcos2)*
*Analista SQA*
