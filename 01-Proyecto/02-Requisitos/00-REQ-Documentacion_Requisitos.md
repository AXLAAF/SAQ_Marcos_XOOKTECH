# Documentación del Proceso de Requisitos (As-Is)

**Responsable:** Analista de Requerimientos  
**Entradas:** Solicitudes informales y vagas del cliente, propuestas preliminares de la línea base y necesidades empíricas del proyecto Visualizador de Marcos.  
**Salidas:** Análisis de conformidad y mapeo de actividades as-is, identificación formal de brechas y listado de artefactos actuales del SGC.  

---

## 1. Introducción y Contexto Metodológico

Esta documentación formaliza el estado actual (As-Is) de la Fase de Requisitos para el proyecto *Visualizador de Marcos*. Enmarcado en el proceso de transición de la organización desde un nivel de madurez empírico e informal (**CMMI Nivel 1 - Inicial**) hacia un sistema controlado y de calidad reproducible (**CMMI Nivel 2 - Gestionado**), este documento analiza la captura y especificación de requerimientos frente al estándar internacional **ISO/IEC/IEEE 12207:2017**.

---

## 2. Propósito y Resultados del Proceso (ISO/IEC/IEEE 12207 6.4.1)

De acuerdo con la norma internacional **ISO/IEC/IEEE 12207:2017 §6.4.1** (Proceso de definición de requisitos del negocio), se definen los siguientes componentes:

*   **Propósito:** Definir los requisitos para un sistema o servicio de software capaz de satisfacer las necesidades operativas de la organización y del cliente en su contexto de negocio, proveyendo una base confiable para la ingeniería de software posterior.
*   **Resultados Esperados (Outcomes):**
    1.  **Identificación de Requisitos:** Las necesidades y expectativas del cliente son identificadas, analizadas y formuladas como requisitos de negocio claros.
    2.  **Evaluación de Impacto:** La viabilidad técnica y el impacto operativo de los requerimientos en el alcance y la arquitectura son evaluados de manera preliminar.
    3.  **Aprobación y Acuerdo:** Los requisitos de negocio son acordados formalmente y mantenidos bajo control de configuración.
    4.  **Trazabilidad:** Se establece y monitorea la trazabilidad bidireccional entre los requisitos y otros artefactos del SGC.

---

## 3. Mapeo de Actividades Actuales (As-Is) de la Organización

El análisis del proceso empírico inicial de la organización frente a las directrices de la ingeniería de software revela el siguiente comportamiento y justificación técnica:

### Actividad 1: Captura Preliminar de Requisitos (WhatsApp y Llamadas)
*   **Paso 1 o Recepción informal:** El cliente o Product Owner externa una idea general por WhatsApp o realiza una llamada de voz rápida detallando una necesidad de negocio informal.
*   **Paso 2 o Ausencia de registro:** La solicitud de requerimiento se queda en la bandeja de chats personales del desarrollador sin registrarse en ningún documento oficial, carpeta física o asignación de folio estructurado.
*   **Paso 3 o Descontrol de alcance:** El desarrollador del equipo comienza a codificar directamente basándose únicamente en su interpretación preliminar del chat, sin un análisis formal de impacto de tiempo, costos o arquitectura.
    *   **Nota Técnica (NT-01):** De acuerdo con **CMMI-DEV v2.0** y **Regan 2002**, la captura informal de requisitos es la principal causa de desvíos en el alcance. Centralizar e identificar de forma única cada petición en una nota física de entrada previene la pérdida de control y formaliza la entrada técnica de requisitos.

### Actividad 2: Especificación y Modelado del Requisito
*   **Paso 1 o Redacción informal:** Se redacta un párrafo corto y ambiguo en lenguaje natural en el cuerpo de una nota descriptiva de la función.
*   **Paso 2 o Ausencia de cotas:** No se establecen límites de formato, peso máximo de archivos, dimensiones permitidas o rendimiento técnico.
*   **Paso 3 o Ambigüedad técnica:** El desarrollador decide de forma arbitraria las reglas de negocio en el backend, imposibilitando que el rol de verificación y pruebas diseñe casos de prueba medibles y objetivos.
    *   **Nota Técnica (NT-02):** **SWEBOK v4.0** y **William E. Lewis 2009** exigen que los requisitos de software sean verificables, medibles y libres de ambigüedad. La adopción de escenarios de aceptación estructurados en formato BDD y cotas numéricas claras provee las bases necesarias para el diseño de casos de prueba robustos.

### Actividad 3: Validación y Aprobación con el Product Owner
*   **Paso 1 o Asunción interna:** El equipo lee el requerimiento redactado de forma interna y asume que cumple con lo que el cliente desea, sin corroborarlo con él.
*   **Paso 2 o Programación directa:** Se inicia la codificación de la funcionalidad en el backend sin presentar la especificación técnica detallada al Product Owner para su revisión formal.
*   **Paso 3 o Rechazo de entrega:** Durante la demostración final, el cliente rechaza la funcionalidad al constatar que el comportamiento real de Flask/OpenCV difiere de lo que él deseaba verbalmente.
    *   **Nota Técnica (NT-03):** **Daniel Galin 2004** conceptualiza la aprobación del cliente como un contrato técnico. **Regan 2002** sustenta que la confirmación escrita explícita en la sección Evidencia de Aprobación es la única evidencia objetiva que deslinda la responsabilidad de SQA ante discrepancias de alcance.

### Actividad 4: Línea Base de Requisitos y Trazabilidad SQA
*   **Paso 1 o Mezcla de archivos:** Las notas aprobadas y pendientes de requisitos se mantienen en la misma carpeta física común sin segregación de archivos.
*   **Paso 2 o Falta de control:** El desarrollador programa tomando notas de forma desordenada, sin saber qué requerimientos están aprobados de forma estable y cuáles están pendientes de cambios.
*   **Paso 3 o Desconexión de pruebas:** No se realiza un mapeo formal hacia los diagramas de diseño lógico de la Fase 03 ni a los casos de prueba de la Fase 04, perdiéndose la trazabilidad en el ciclo de vida del desarrollo.
    *   **Nota Técnica (NT-04):** **CMMI-DEV v2.0** y **William E. Lewis 2009** exigen el control de configuración físico para proteger la Línea Base estable. SQA requiere trazabilidad bidireccional desde el requerimiento hasta el código y los casos de prueba para garantizar la cobertura del 100% y facilitar el análisis de impacto.

---

## 4. Catálogo de Artefactos de Requisitos Existentes

La línea base actual cuenta con los siguientes artefactos físicos de requisitos registrados y refactorizados en el SGC:

| ID de Archivo | Nombre del Artefacto                   | Estado de Calidad | Ubicación en Bóveda                                                                       |
| ------------- | -------------------------------------- | ----------------- | ----------------------------------------------------------------------------------------- |
| `REQ-01`      | Carga de Imagen de Fondo               | Aprobado          | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen.md`           |
| `REQ-04`      | Catálogo de Marcos Disponibles         | Aprobado          | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos.md`        |
| `REQ-05`      | Filtrado del Catálogo de Marcos        | Aprobado          | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo.md`      |
| `REQ-02`      | Previsualización de Imagen con Marco   | Aprobado          | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco.md` |
| `REQ-07`      | Visualización de Marcos Dobles         | Aprobado          | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/07-REQ-07_Marcos_Dobles.md`          |
| `REQ-08`      | Selección de Tipo de Vidrio            | Pendiente         | `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/08-REQ-08_Tipo_Vidrio.md`           |
| `REQ-09`      | Simulación de María Luisa              | Pendiente         | `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/09-REQ-09_Maria_Luisa.md`           |
| `REQ-10`      | Proyección en Pantalla Secundaria      | Pendiente         | `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria.md`   |
| `STD-03`      | Matriz de Trazabilidad RTM             | Sincronizada      | `02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad.md`                 |
| `REG-02-01`   | Registro de Verificación de Requisitos | Activo            | `02-Requisitos/02-Calidad_Requisitos/REG-02-01_Verificacion_Requisitos.md`                |

---

## 5. Análisis de Brechas Identificadas frente al Estándar

Al contrastar la práctica as-is contra las directrices de **ISO/IEC/IEEE 12207 6.4.1**, se han detectado las siguientes brechas en el SGC:

1.  **Carencia de Plantillas Estructuradas Estandarizadas (Gap-01):** Aunque los requisitos actuales poseen escenarios BDD, no existe una plantilla unificada oficial y vacía (ej. `PLT-SRS.md`) que garantice que futuras solicitudes sigan exactamente la misma estructura técnica e institucional de calidad.
2.  **Ausencia de una SRS espesifica bajo Normativa (Gap-02):** La organización carece de un documento formal de Especificación de Requisitos de Software (SRS) que centralice el alcance global bajo estándares (como **IEEE Std 830** o **ISO/IEC/IEEE 29148**).
3.  **Checklists de Calidad no Segregados por Artefacto (Gap-03):** Las revisiones de SQA se realizan de forma genérica. Se requiere un checklist especializado (ej. `CHK-SRS.md`) enfocado en validar las 6 características de la norma IEEE 830.

---

## 6. Control de Entregables Generados

A continuación se detalla la gobernanza del presente documento de proceso:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Documentación del Proceso de Requisitos (As-Is) | REQ-DOC-01 | ISO/IEC/IEEE 12207:2017 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
