# Plan de Mejora de Diseño (To-Be)

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Documentación del proceso de diseño (As-Is), catálogo de brechas de arquitectura de software y directrices de calidad de CMMI Nivel 2.  
**Salidas:** Modelo del proceso de diseño to-be, matriz de implementación de prácticas CMMI-DEV v2.0 TS, métricas de calidad de diseño y criterios de verificación SQA.  

---

## 1. Introducción y Nivel de Madurez

El presente plan establece el modelo de proceso optimizado (To-Be) para la Fase de Diseño del proyecto *Visualizador de Marcos*. El diagnóstico organizacional sitúa a la empresa en un **Nivel 1 (Inicial)** de madurez de procesos de software en diseño: la codificación se realiza de manera empírica e inmediata sin previa validación arquitectónica formal, provocando problemas de consistencia tecnológica e interfaces rotas.

El objetivo estratégico es escalar al **Nivel 2 (Gestionado)** de **CMMI-DEV v2.0**, garantizando que el diseño del software se modele, verifique y traze formalmente antes de iniciar la construcción, permitiendo así una transición ordenada e impecable a la codificación.

---

## 2. Área de Proceso Aplicable: Technical Solution (TS)

Para satisfacer las demandas de CMMI Nivel 2, se adopta el área de proceso **Technical Solution (TS)**. Su objetivo es seleccionar, diseñar e implementar soluciones técnicas para satisfacer los requisitos del negocio, del cliente y del producto, garantizando que el paquete de diseño guíe rigurosamente el desarrollo físico.

---

## 3. Prácticas Específicas CMMI (SP 1.1 a SP 2.2) e Implementación

El proceso de diseño To-Be se estructurará mediante la implementación de las siguientes prácticas específicas de Solución Técnica:

### SP 1.1: Seleccionar Soluciones de Componentes de Producto
*   **Implementación:** Se evalúan formalmente las alternativas tecnológicas para el procesamiento de imágenes (ej. Flask vs FastAPI, OpenCV vs Pillow puro) y persistencia de datos. Las decisiones técnicas se consolidan y justifican en el documento SDD.
*   **Justificación Técnica (NT-01):** Según **Daniel Galin 2004** y **SWEBOK v4.0**, la selección fundamentada de componentes técnicos previene inconsistencias de compatibilidad física a mitad del ciclo de desarrollo y optimiza el consumo de recursos de cómputo en producción.

### SP 1.2: Desarrollar Diseños Detallados de Componentes
*   **Implementación:** Se define el uso mandatorio de la plantilla oficial de Documento de Descripción de Diseño (`PLT-SDD.md`) basada en la norma **IEEE Std 1016**, detallando las vistas de descomposición de software, flujos de estados lógicos y esquemas de datos del Visualizador de Marcos.
*   **Justificación Técnica (NT-02):** **William E. Lewis 2009** destaca que describir detalladamente cada componente del software mitiga la ambigüedad en el desarrollo y sienta las bases para que el equipo de pruebas verifique el comportamiento contra especificaciones del diseño lógico y físico.

### SP 2.1: Diseñar las Interfaces de los Componentes
*   **Implementación:** Se formalizan y congelan en el documento SDD las interfaces lógicas de programación de software (APIs, rutas de Flask, parámetros y signaturas de funciones de OpenCV) antes de iniciar la codificación física en Git.
*   **Justificación Técnica (NT-03):** De acuerdo con **Regan 2002**, el diseño de interfaces robustas previene la desalineación entre componentes y garantiza la integración continua de subsistemas de software sin fallos lógicos durante el ensamblaje.

### SP 2.2: Establecer un Paquete de Diseño Técnico
*   **Implementación:** Se centralizan todos los diagramas en Mermaid.js (`STD-04` a `STD-07`) bajo un paquete unificado y controlado en la carpeta `03-Diseño/`. El paquete de diseño resultante se establece como el insumo de entrada (*Entry Criteria*) inamovible para iniciar el proceso `PROC-04_Codificacion`.
*   **Justificación Técnica (NT-04):** **CMMI-DEV v2.0** establece que el paquete de diseño técnico estructurado y bajo control de configuración es el único medio seguro para transferir la arquitectura lógica a los programadores del software.

---

## 4. Métricas de Calidad de Diseño

Para monitorear y garantizar la excelencia del proceso To-Be, se implementan las siguientes tres métricas cuantitativas básicas:

1.  **Densidad de Defectos de Diseño (DDD):**
    $$\text{DDD} = \frac{\text{Defectos de Diseño Detectados en Inspecciones}}{\text{Total de Componentes Diseñados}}$$
    *   *Meta:* $\le 0.10$ defectos por componente lógico antes de la liberación a desarrollo.
2.  **Cobertura de Requisitos en el Diseño (CRD):**
    $$\text{CRD} = \left( \frac{\text{Requisitos Mapeados a Elementos de Diseño en RTM}}{\text{Total de Requisitos Aprobados}} \right) \times 100$$
    *   *Meta:* $100\%$ de cobertura de requisitos en el diseño obligatoria.
3.  **Alineación de Interfaces de Software (AIS):**
    $$\text{AIS} = \left( \frac{\text{Interfaces Codificadas que Respetan el Diseño}}{\text{Total de Interfaces Implementadas}} \right) \times 100$$
    *   *Meta:* $100\%$ de alineación en interfaces físicas respecto a la especificación SDD.

---

## 5. Criterios de Éxito y Verificación

El éxito del plan de mejora en diseño se evaluará periódicamente en las auditorías de calidad bajo los siguientes criterios objetivos:

*   **Conformidad Documental:** El 100% de los artefactos de diseño cumplen estrictamente con la estructura formal de XookTech v2.0, están libres de YAML Frontmatter y cuentan con su respectivo ETVX.
*   **Inspección del Diseño:** Todo documento de diseño modificado o de nueva creación ha sido verificado mediante el checklist formal `CHK-SDD.md` antes de incorporarse a la línea base de producción.
*   **Integración de Vistas:** El paquete de diseño unificado incluye de forma explícita los diagramas del sistema en Mermaid.js y el mapeo en la Matriz de Trazabilidad RTM.

---

## 6. Control de Entregables Generados

A continuación se detalla la gobernanza del presente plan de mejora:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Plan de Mejora de Diseño (To-Be) | DIS-PLM-01 | CMMI-DEV v2.0 - TS | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
