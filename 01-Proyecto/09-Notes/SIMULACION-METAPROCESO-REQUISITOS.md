# Simulación de Ejecución del Metaproceso de Requisitos

**Código de Registro:** SIM-09-03  
**Responsable de Redacción:** Analista de Gobernanza y Diseño  
**Fecha de Elaboración:** 24 de Mayo de 2026  
**Entradas:** Directrices metodológicas de `MET-09-02`, solicitudes de requerimientos empíricos iniciales del Product Owner y plantilla de requerimiento `TEMPLATE-REQ`.  
**Salidas:** Simulación paso a paso del ciclo de vida del metaproceso, ficha de requerimiento formal de ingeniería (BDD), checklist SQA de verificación y registro de aprobación para la Línea Base.  
**Propósito:** Simular de forma exhaustiva y práctica la ejecución del metaproceso de ingeniería y control de calidad SQA sobre la Fase 02 - Requisitos, utilizando un caso real del proyecto para demostrar cómo la justificación científica transforma sugerencias empíricas en artefactos certificados.

---

## 1. Introducción y Propósito de la Simulación

Esta nota técnica presenta la **simulación práctica** de la ejecución del metaproceso de requisitos. Para demostrar su viabilidad y efectividad organizativa, recreamos paso a paso el ciclo de vida del requerimiento crítico **REQ-01: Carga de Imagen del Cliente**. 

El objetivo es evidenciar la maquinaria de reingeniería de XookTech en acción, mostrando cómo una solicitud informal se somete a la disciplina de ingeniería de requisitos y al control estricto de aseguramiento de calidad (SQA) antes de ingresar oficialmente a la Línea Base del SGC.

---

## 2. Fase de Ingeniería: Simulación de Construcción del Artefacto

### Paso 1: Recepción de la Entrada Empírica (El Estado Inicial)
El metaproceso inicia cuando el *Analista de Requerimientos* recibe la solicitud original del Product Owner (PO) en formato verbal o correo electrónico:

> **Solicitud Inicial del PO (Mensaje de WhatsApp - 12/03/2026):**  
> *"Hola, para el visualizador necesitamos que el cliente pueda subir una foto de su celular desde la página web, que cargue rápido y que no acepte formatos raros, solo fotos comunes. Debe verse bien en la pantalla."*

---

### Paso 2: Análisis de Fallas y Nota Técnica (El Detonante SQA)
El analista identifica las carencias y riesgos de calidad en la solicitud del PO:
1.  **Ambigüedad Semántica:** Las expresiones *"que cargue rápido"* y *"fotos comunes"* no son medibles ni comprobables por el equipo de pruebas. ¿Qué es rápido? ¿Qué es común?
2.  **Falta de Restricciones:** No se definen límites de tamaño de archivo ni validaciones de formatos MIME en el backend de Flask, lo que representa una vulnerabilidad de seguridad e inestabilidad del servidor.

**Justificación Bibliográfica (SWEBOK v4 / Regan 2002):**  
Para evitar la ambigüedad y la deuda técnica, se aplica el formato BDD (*Behavior-Driven Development*), estructurando las reglas de negocio en escenarios explícitos: **Dado [Contexto] / Cuando [Acción] / Entonces [Resultado esperado]**. Esto transforma la sugerencia en un requerimiento atómico, verificable y viable.

---

### Paso 3: Redacción de la Ficha de Requisito Formal (El Artefacto de Ingeniería)
El analista utiliza la plantilla institucional `TEMPLATE-REQ` para modelar y estructurar la ficha de requerimiento técnico.

#### [Ficha de Requisito Simulada]

##### Identificador Único: REQ-01
*   **Nombre:** Carga de Imagen del Cliente
*   **Fase del SGC:** 02 - Especificación de Requerimientos
*   **Rol Responsable:** Analista de Requerimientos
*   **Descripción Funcional:** El sistema debe proveer una interfaz web responsiva que permita al usuario cargar un archivo de imagen local (JPEG/PNG) para proyectarla en el visualizador interactivo de marcos, implementando validaciones estrictas en el cliente y en el servidor.

##### Reglas de Negocio Estrictas:
1.  **Formatos Permitidos:** Exclusivamente extensiones `.jpg`, `.jpeg` y `.png`.
2.  **Peso Máximo de Archivo:** Límite máximo de 10 MB para evitar saturación de memoria en el servidor OpenCV/Flask.
3.  **Retroalimentación de Interfaz:** Si el archivo es inválido, el sistema debe desplegar un mensaje de alerta visible sin recargar la página.

##### Escenarios de Aceptación (Formato BDD):

*   **Escenario 1: Carga Exitosa de Imagen Válida**
    *   **Dado** que el cliente se encuentra en la pantalla de previsualización del visualizador de marcos,
    *   **Cuando** selecciona y sube un archivo de imagen en formato `JPEG` con un tamaño de `4.2 MB`,
    *   **Entonces** el sistema debe validar el formato y tamaño del archivo en el servidor,
    *   **Y** renderizar con éxito la imagen en el canvas interactivo en un tiempo inferior a `1.5 segundos`.

*   **Escenario 2: Rechazo de Formato Inválido**
    *   **Dado** que el cliente está en el formulario de carga de imagen,
    *   **Cuando** intenta subir un archivo con extensión `.gif` o `.pdf`,
    *   **Entonces** el sistema debe bloquear la carga en el cliente,
    *   **Y** desplegar una alerta con el mensaje: *"Error: Formato de archivo no permitido. Solo se aceptan imágenes JPG y PNG."*

*   **Escenario 3: Rechazo por Exceso de Peso**
    *   **Dado** que el cliente está en la interfaz de carga,
    *   **Cuando** sube una imagen válida `PNG` pero con un peso de `12.5 MB` (que excede el límite de 10 MB),
    *   **Entonces** el backend de Flask debe rechazar la petición HTTP con un código de error `413 Payload Too Large`,
    *   **Y** notificar al usuario que la imagen supera el límite de peso permitido.

---

## 3. Fase de Aseguramiento de Calidad: Simulación de Validación SQA

Una vez que el *Analista de Requerimientos* concluye la redacción técnica (Fase de Ingeniería), el artefacto **no** se ingresa de inmediato a la Línea Base. Se activa el protocolo SQA, y el *Analista de Control y Cambios* ejecuta una auditoría de conformidad utilizando el checklist **CL-02**.

### Paso 1: Simulación de Auditoría SQA (Checklist CL-02)

| Criterio de Calidad (SWEBOK / Galin) | Estado de Cumplimiento | Evidencia Técnica / Notas SQA |
| :--- | :---: | :--- |
| **1. Atómico:** ¿El requerimiento describe una única función del sistema? | **APROBADO** | Describe exclusivamente la funcionalidad de carga y validación de la imagen. |
| **2. Sin Ambigüedad:** ¿Los escenarios están redactados bajo estructura medible (BDD)? | **APROBADO** | Se eliminó el lenguaje subjetivo. Se definieron límites en segundos (1.5s) y megabytes (10MB). |
| **3. Verificable:** ¿El equipo de pruebas puede diseñar casos de prueba con los criterios dados? | **APROBADO** | Los escenarios BDD proveen directamente las precondiciones, acciones y resultados esperados para la Fase 05. |
| **4. Completo:** ¿Se contemplan flujos alternos y de error en el backend? | **APROBADO** | Se incluyeron escenarios explícitos para el peso excesivo y formatos no admitidos. |
| **5. Trazable:** ¿El requerimiento tiene un folio único asignado para la matriz RTM? | **APROBADO** | Identificado como REQ-01. |

---

### Paso 2: Generación del Registro de Aprobación (Registro REG-02-01)
El *Analista de Control y Cambios* emite el dictamen de calidad formal en el registro:

#### [Registro de Aprobación de Calidad Simulada]

*   **ID de Registro:** REG-02-01-REQ-01
*   **Artefacto Evaluado:** Ficha de Requerimiento `REQ-01: Carga de Imagen`
*   **Fecha de Evaluación:** 24 de Mayo de 2026
*   **Auditor SQA Responsable:** Analista de Control y Cambios
*   **Dictamen Final:** **APROBADO PARA LÍNEA BASE**
*   **Justificación del Dictamen:** El requerimiento cumple satisfactoriamente con el 100% de los criterios del checklist `CL-02`. Los escenarios BDD eliminan la ambigüedad, y las reglas técnicas de negocio proveen directrices claras para la codificación y pruebas unitarias. Se autoriza su congelamiento y traslado al directorio `01-Aprobados`.

---

## 4. Transición del Artefacto a "Verdadero Proceso" (Línea Base)

Una vez firmado el dictamen de SQA, el metaproceso ejecuta las acciones automatizadas de control de configuración:
1.  **Congelamiento y Traslado:** El archivo `REQ-01_Carga_Imagen.md` se mueve físicamente al directorio oficial `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen.md`.
2.  **Actualización de la Matriz RTM:** El *Analista de Requerimientos* incorpora el ID `REQ-01` en el documento `01-STD-03_Matriz_Trazabilidad.md`, vinculándolo con su caso de diseño de arquitectura (`STD-04 Componentes`) y los casos de prueba correspondientes (`CP-01`, `CP-02`, `CP-03` en la Fase 05).
3.  **Uso en el Ciclo de Vida (El Verdadero Proceso):**
    *   *Entrada a Desarrollo (Fase 04):* El desarrollador toma los límites de 10 MB y JPEG/PNG para escribir la validación Flask.
    *   *Entrada a Pruebas (Fase 05):* El tester toma los 3 escenarios BDD para escribir y automatizar las pruebas unitarias e integrales en Python.

```
[Minuta de Alineación Metodológica]
              |
              v
[Metaproceso (MET-09-02)] detona la creación de:
              |
              +---> [PROC-02 (Ingeniería)] ---> Genera REQ-01 BDD
              |
              +---> [CL-02 (SQA)] ------------> Audita REQ-01 BDD
              |
              +---> [REG-02-01 (QA)] ---------> Firma Aprobación SQA
                                                   |
                                                   v
                                     [LÍNEA BASE CERTIFICADA]
                                     (02-Requisitos/01-Aprobados)
```

---

## 5. Conclusión y Lecciones SQA de la Simulación

Esta simulación demuestra que la implementación del metaproceso de requisitos bajo el estándar de **XookTech v2.0**:
*   **Elimina la improvisación:** Cada requerimiento pasa por un filtro de ingeniería riguroso y una validación independiente de calidad.
*   **Garantiza la paridad:** Previene la acumulación de deuda técnica y de control, proveyendo al equipo de desarrollo y pruebas de insumos contractuales libres de ambigüedad.
*   **Institucionaliza el SGC:** Evidencia de forma práctica al profesor que el equipo comprende e implementa el rigor de Aseguramiento de Calidad, convirtiendo la teoría de la materia en una metodología sistemática y certificada al 100.00%.
