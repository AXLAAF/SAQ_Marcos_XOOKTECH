# Documentación del Proceso de Diseño (As-Is)

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Requisitos aprobados en la fase de ingeniería de requerimientos, diagramas empíricos de flujo de sistema y componentes informales de software.  
**Salidas:** Análisis de conformidad y mapeo de actividades as-is de diseño, catálogo de estándares técnicos y análisis de brechas de arquitectura bajo ISO/IEC 12207.  

---

## 1. Introducción y Contexto Metodológico

Esta documentación formaliza el estado actual (As-Is) del proceso de diseño en el proyecto *Visualizador de Marcos*. La organización se encuentra en la transición metodológica desde prácticas de codificación directa sin diseño formalizado (**CMMI Nivel 1 - Inicial**) hacia un entorno estructurado de diseño técnico verificable (**CMMI Nivel 2 - Gestionado**). Este documento evalúa las actividades de arquitectura de software frente al estándar internacional **ISO/IEC/IEEE 12207:2017**.

---

## 2. Propósito y Resultados del Proceso (ISO/IEC/IEEE 12207 §6.4.4)

De acuerdo con la norma internacional **ISO/IEC/IEEE 12207:2017 §6.4.4** (Proceso de diseño de la arquitectura del sistema), se definen los siguientes componentes:

*   **Propósito:** Proporcionar un diseño para el sistema que implemente los requisitos del sistema y que sea verificable frente a ellos, detallando la descomposición del software en componentes con interfaces claras para guiar la codificación.
*   **Resultados Esperados (Outcomes):**
    1.  **Definición Arquitectónica:** Se define la arquitectura del sistema identificando sus componentes, subsistemas e interfaces de comunicación.
    2.  **Verificación y Consistencia:** Se analiza y verifica la consistencia del diseño de software frente a la línea base de requisitos aprobados.
    3.  **Trazabilidad del Diseño:** Se establece la trazabilidad bidireccional entre los requisitos del negocio y los elementos de diseño técnico.

---

## 3. Mapeo de Actividades Actuales (As-Is) vs Estándar

La operación actual del proceso de diseño se describe a través de los siguientes flujos de trabajo e interpretaciones técnicas:

### Actividad 1: Modelado de Diagrama de Componentes
1.  **Paso 1 - Recuperar requerimiento:** El Analista de Gobernanza y Diseño toma la ficha de requerimiento aprobada (ej. `REQ-01`) de la Fase 02.
2.  **Paso 2 - Diseño de arquitectura lógica:** Diseña la estructura interna del sistema mediante diagramas de componentes utilizando lenguaje descriptivo Mermaid.js.
3.  **Paso 3 - Registro del estándar:** Registra la vista técnica bajo la nomenclatura estructurada `01-STD-04_Diagrama_Componentes.md` para control del SGC.
    *   **Nota Técnica (NT-01):** Según **Daniel Galin 2004**, modelar la descomposición física y lógica de los componentes de software antes de iniciar la construcción reduce hasta en un 40% el retrabajo en la fase de codificación, aislando la lógica de negocio de los detalles de infraestructura.

### Actividad 2: Modelado del Flujo y Navegación del Sistema
1.  **Paso 1 - Definir ciclo de navegación:** Se traza el camino de interacción del usuario con la interfaz de visualización de marcos de Flask y OpenCV.
2.  **Paso 2 - Modelado de estados:** Se definen los flujos lógicos, llamadas a funciones del backend y respuestas de la vista del cliente.
3.  **Paso 3 - Almacenamiento en SGC:** Se resguarda en el artefacto `02-STD-05_Flujo_Sistema.md`.
    *   **Nota Técnica (NT-02):** **SWEBOK v4.0** destaca que la diagramación del flujo dinámico del sistema y la interacción de componentes de software permite detectar de forma proactiva bloqueos mutuos (*deadlocks*) e inconsistencias lógicas en el comportamiento del backend.

### Actividad 3: Definición del Modelo de Datos
1.  **Paso 1 - Identificación de estructuras:** Se definen las tablas de base de datos o esquemas JSON que almacenarán el catálogo de marcos, dimensiones y tipos de vidrio.
2.  **Paso 2 - Modelado entidad-relación:** Se describe el modelo de datos en `03-STD-06_Modelo_Datos.md` con sus tipos de datos y llaves primarias.
3.  **Paso 3 - Sincronización:** Se valida que el modelo sea capaz de respaldar los escenarios de persistencia requeridos por desarrollo.
    *   **Nota Técnica (NT-03):** **William E. Lewis 2009** postula que el modelo de datos es la base de la persistencia de software y debe estar documentado formalmente para evitar corrupción en el almacenamiento y discrepancias en los esquemas entre ambientes.

### Actividad 4: Mapeo de la Arquitectura Física Python
1.  **Paso 1 - Diseño del esqueleto:** Se describe el mapa físico del repositorio, ubicando directorios clave como `app/`, `static/`, `templates/` y archivos de configuración.
2.  **Paso 2 - Definición de interfaces de software:** Se registran las signaturas de las funciones esenciales de Flask y procesamiento de imágenes con OpenCV.
3.  **Paso 3 - Registro en SGC:** Se almacena en `04-STD-07_Arquitectura_Python.md`.
    *   **Nota Técnica (NT-04):** **CMMI-DEV v2.0** establece que documentar el esqueleto físico del proyecto es un prerrequisito indispensable para asegurar que el equipo de desarrollo codifique de forma estructurada e incorporando estándares comunes de arquitectura.

---

## 4. Catálogo de Artefactos de Diseño Existentes

La fase de diseño actual cuenta con los siguientes artefactos registrados en la bóveda de Obsidian:

| ID de Archivo | Nombre del Artefacto | Estado de Calidad | Ubicación en Bóveda |
|---|---|---|---|
| `STD-04` | Diagrama de Componentes Lógicos | Aprobado | `03-Diseño/01-Ingenieria_Diseño/01-STD-04_Diagrama_Componentes.md` |
| `STD-05` | Diagrama de Flujo del Sistema | Aprobado | `03-Diseño/01-Ingenieria_Diseño/02-STD-05_Flujo_Sistema.md` |
| `STD-06` | Modelo de Datos y Esquemas | Aprobado | `03-Diseño/01-Ingenieria_Diseño/03-STD-06_Modelo_Datos.md` |
| `STD-07` | Estructura Física y Arquitectura Python | Aprobado | `03-Diseño/01-Ingenieria_Diseño/04-STD-07_Arquitectura_Python.md` |
| `HALLAZGO-01`| Registro de Inconsistencia Tecnológica| Resuelto | `03-Diseño/02-Calidad_Diseño/HALLAZGO-01_Inconsistencia_Tecnologica.md` |
| `PROC-03` | Proceso de Diseño de Sistema | Vigente | `03-Diseño/03-PROC-03_Diseño_Sistema.md` |

---

## 5. Análisis de Brechas Identificadas frente al Estándar

Al contrastar la práctica as-is contra las directrices de **ISO/IEC/IEEE 12207 §6.4.4**, se detectan las siguientes brechas:

1.  **Carencia de un Documento Integrador de Descripción de Diseño (Gap-01):** Los diagramas técnicos actuales (`STD-04` a `STD-07`) están aislados. Se requiere una plantilla formal de Documento de Descripción de Diseño de Software (SDD) basada en **IEEE Std 1016** (ej. `PLT-SDD.md`) que unifique las vistas arquitectónicas lógicas y físicas.
2.  **Ausencia de una Plantilla de Diagramación de Arquitectura bajo Estándar (Gap-02):** No se cuenta con una guía estandarizada para estructurar nuevos diagramas arquitectónicos que guíen al equipo en la adición de módulos bajo el enfoque de puntos de vista (*viewpoints*) de IEEE 1016.
3.  **Checklist de Calidad de Diseño Inexistente (Gap-03):** Las evaluaciones de SQA carecen de una herramienta formal estructurada para validar la integridad del diseño. Se requiere un checklist específico (`CHK-SDD.md`) basado en la norma IEEE 1016.

---

## 6. Control de Entregables Generados

A continuación se detalla la gobernanza del presente documento de proceso:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Documentación del Proceso de Diseño (As-Is) | DIS-DOC-01 | ISO/IEC/IEEE 12207:2017 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
