# Documentación del Proceso de Requisitos (As-Is)

**Responsable:** Analista de Requerimientos  
**Entradas:** Solicitudes informales y vagas del cliente, propuestas preliminares de la línea base y necesidades empíricas del proyecto Visualizador de Marcos.  
**Salidas:** Análisis de conformidad y mapeo de actividades as-is, identificación formal de brechas y listado de artefactos actuales del SGC.  

---

## 1. Introducción y Contexto Metodológico

Esta documentación formaliza el estado actual (As-Is) de la Fase de Requisitos para el proyecto *Visualizador de Marcos*. Enmarcado en el proceso de transición de la organización desde un nivel de madurez empírico e informal (**CMMI Nivel 1 - Inicial**) hacia un sistema controlado y de calidad reproducible (**CMMI Nivel 2 - Gestionado**), este documento analiza la captura y especificación de requerimientos frente al estándar internacional **ISO/IEC/IEEE 12207:2017**.

---

## 2. Propósito y Resultados del Proceso (ISO/IEC/IEEE 12207 §6.4.1)

De acuerdo con la norma internacional **ISO/IEC/IEEE 12207:2017 §6.4.1** (Proceso de definición de requisitos del negocio), se definen los siguientes componentes:

*   **Propósito:** Definir los requisitos para un sistema o servicio de software capaz de satisfacer las necesidades operativas de la organización y del cliente en su contexto de negocio, proveyendo una base confiable para la ingeniería de software posterior.
*   **Resultados Esperados (Outcomes):**
    1.  **Identificación de Requisitos:** Las necesidades y expectativas del cliente son identificadas, analizadas y formuladas como requisitos de negocio claros.
    2.  **Evaluación de Impacto:** La viabilidad técnica y el impacto operativo de los requerimientos en el alcance y la arquitectura son evaluados de manera preliminar.
    3.  **Aprobación y Acuerdo:** Los requisitos de negocio son acordados formalmente y mantenidos bajo control de configuración.
    4.  **Trazabilidad:** Se establece y monitorea la trazabilidad bidireccional entre los requisitos y otros artefactos del SGC.

---

## 3. Mapeo de Actividades Actuales (As-Is) vs Estándar

El análisis detallado de la operación empírica inicial frente a las mejores prácticas de la ingeniería de software revela el siguiente comportamiento y justificación técnica:

### Actividad 1: Captura Preliminar de la Solicitud de Negocio
1.  **Paso 1 - Recepción informal:** El cliente o Product Owner externa una idea general por canales no oficiales (llamadas telefónicas o mensajes de WhatsApp) sin estructura documental fija.
2.  **Paso 2 - Registro manual en Bóveda:** El Analista de Requerimientos recupera manualmente la solicitud y la registra en formato de nota física dentro de la carpeta `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/`.
3.  **Paso 3 - Asignación de Folio:** Se le asigna una nomenclatura estructurada provisional (ej: `REQ-XX`) para incorporarla formalmente al control de la bóveda de Obsidian.
    *   **Nota Técnica (NT-01):** Según **Daniel Galin 2004**, la captura informal de requisitos, si no se canaliza de inmediato mediante una nota de entrada protegida, es la principal fuente de desvíos en el alcance del proyecto. El aislamiento físico de las peticiones en carpetas de "pendientes" constituye el primer paso hacia el control de configuración formal.

### Actividad 2: Especificación y Modelado del Requisito
1.  **Paso 1 - Aplicación de formato:** La nota de entrada se expande de un texto simple a un modelo descriptivo con reglas de negocio limitantes (dimensiones permitidas, formatos de imagen aceptados y cotas numéricas).
2.  **Paso 2 - Redacción de Escenarios BDD:** El Analista de Requerimientos traduce la lógica de negocio a escenarios de aceptación legibles empleando la estructura de lenguaje ubicuo `Dado / Cuando / Entonces`.
3.  **Paso 3 - Mapeo bidireccional preliminar:** El ID del requisito es agregado de inmediato en la Matriz de Trazabilidad para vigilar su ciclo de vida y evitar orfandad del artefacto.
    *   **Nota Técnica (NT-02):** **SWEBOK v4.0** y **William E. Lewis 2009** destacan que la especificación basada en comportamiento (BDD) disminuye significativamente la ambigüedad en la interpretación y facilita al rol de verificación el diseño de casos de prueba medibles y ejecutables desde etapas tempranas.

### Actividad 3: Revisión de Aprobación Contractual
1.  **Paso 1 - Presentación técnica:** El Analista de Requerimientos expone la ficha técnica en formato BDD al Product Owner para su revisión formal.
2.  **Paso 2 - Conciliación:** Se resuelven de forma colaborativa posibles discrepancias y dudas sobre las fronteras tecnológicas del Visualizador de Marcos.
3.  **Paso 3 - Cierre despersonalizado:** Una vez acordado, se actualiza el estado en la bóveda a "Aprobado" y se adjunta la autorización digital institucional bajo el estándar.
    *   **Nota Técnica (NT-03):** De acuerdo con **Regan 2002**, la firma y el acuerdo explícito de requerimientos actúan como un contrato de software y deslindan responsabilidades de SQA ante solicitudes posteriores de cambio no planificadas.

### Actividad 4: Inyección en la Línea Base de Requisitos
1.  **Paso 1 - Segregación física:** El Analista de Requerimientos mueve el archivo `.md` de la carpeta `00-Pendientes/` a la carpeta `01-Aprobados/`.
2.  **Paso 2 - Congelamiento de versión:** Se actualizan las tablas de trazabilidad y la línea base del sistema para reflejar el estado estable de la configuración.
3.  **Paso 3 - Auditoría de Calidad SQA:** El Analista de Control y Cambios evalúa periódicamente la ficha de requerimiento aprobada empleando checklists estructurados para garantizar el cumplimiento documental.
    *   **Nota Técnica (NT-04):** **CMMI-DEV v2.0** (Requirements Management) describe que proteger físicamente las versiones aprobadas impide la inyección descontrolada de alcance (*scope creep*) y garantiza que los desarrolladores programen sobre bases estables y autorizadas.

---

## 4. Catálogo de Artefactos de Requisitos Existentes

La línea base actual cuenta con los siguientes artefactos físicos de requisitos registrados y refactorizados en el SGC:

| ID de Archivo | Nombre del Artefacto | Estado de Calidad | Ubicación en Bóveda |
|---|---|---|---|
| `REQ-01` | Carga de Imagen de Fondo | Aprobado | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen.md` |
| `REQ-04` | Catálogo de Marcos Disponibles | Aprobado | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos.md` |
| `REQ-05` | Filtrado del Catálogo de Marcos | Aprobado | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo.md` |
| `REQ-02` | Previsualización de Imagen con Marco | Aprobado | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco.md` |
| `REQ-07` | Visualización de Marcos Dobles | Aprobado | `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/07-REQ-07_Marcos_Dobles.md` |
| `REQ-08` | Selección de Tipo de Vidrio | Pendiente | `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/08-REQ-08_Tipo_Vidrio.md` |
| `REQ-09` | Simulación de María Luisa | Pendiente | `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/09-REQ-09_Maria_Luisa.md` |
| `REQ-10` | Proyección en Pantalla Secundaria | Pendiente | `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/10-REQ-10_Pantalla_Secundaria.md` |
| `STD-03` | Matriz de Trazabilidad RTM | Sincronizada | `02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad.md` |
| `REG-02-01`| Registro de Verificación de Requisitos| Activo | `02-Requisitos/02-Calidad_Requisitos/REG-02-01_Verificacion_Requisitos.md` |

---

## 5. Análisis de Brechas Identificadas frente al Estándar

Al contrastar la práctica as-is contra las directrices de **ISO/IEC/IEEE 12207 §6.4.1**, se han detectado las siguientes brechas críticas en el SGC:

1.  **Carencia de Plantillas Estructuradas Estandarizadas (Gap-01):** Aunque los requisitos actuales poseen escenarios BDD, no existe una plantilla unificada oficial y vacía (ej. `PLT-SRS.md`) que garantice que futuras solicitudes sigan exactamente la misma estructura técnica e institucional de calidad.
2.  **Ausencia de una SRS Consolidada bajo Normativa (Gap-02):** La organización carece de un documento formal de Especificación de Requisitos de Software (SRS) que centralice el alcance global bajo estándares de reconocimiento académico (como **IEEE Std 830** o **ISO/IEC/IEEE 29148**).
3.  **Checklists de Calidad no Segregados por Artefacto (Gap-03):** Las revisiones de SQA se realizan de forma genérica. Se requiere un checklist especializado (ej. `CHK-SRS.md`) enfocado en validar las 6 características de la norma IEEE 830.

---

## 6. Control de Entregables Generados

A continuación se detalla la gobernanza del presente documento de proceso:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Documentación del Proceso de Requisitos (As-Is) | REQ-DOC-01 | ISO/IEC/IEEE 12207:2017 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
