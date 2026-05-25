# Checklist de Calidad para la Matriz de Trazabilidad (CHK-RTM)
**Responsable:** Analista de Requerimientos  
**Entradas:** Matriz de Trazabilidad de Requisitos (RTM) (`01-STD-03_Matriz_Trazabilidad.md`), listado oficial de requisitos aprobados y repositorio de casos de prueba y diseño.  
**Salidas:** Evaluación de consistencia y bidireccionalidad de la matriz de trazabilidad bajo prácticas CMMI.  

---

## 1. Instrucciones de Uso

Este checklist es el mecanismo de verificación de calidad obligatorio para asegurar que la Matriz de Trazabilidad de Requisitos (RTM) esté perfectamente alineada con las directrices de **CMMI-DEV v2.0 REQM SP 1.4**. El **Analista de Requerimientos** debe ejecutar este control de forma periódica sobre la matriz. Cada criterio debe ser validado y marcado con una `[x]` solo si se cumple en su totalidad.

---

## 2. Criterios de Evaluación de Calidad

### 2.1 Cobertura y Completitud de la Línea Base (REQM SP 1.4)
- [ ] **M-01: Inclusión Total:** ¿La matriz incluye el 100% de los requisitos funcionales y no funcionales que componen la Línea Base aprobada oficial del proyecto?
- [ ] **M-02: Mapeo de Origen:** ¿Cada requisito está explícitamente vinculado a su fuente primaria de origen (Contrato de Desarrollo, Acta de Junta o Solicitud de Cambio `CR-XXX`)?
- [ ] **M-03: Mapeo de Diseño:** ¿Cada requisito aprobado tiene asociado su correspondiente diagrama de arquitectura o flujo de sistema de la Fase 03?
- [ ] **M-04: Mapeo de Verificación:** ¿Cada requisito tiene vinculados los Casos de Prueba (`CP-XX`) específicos de la Fase 05 diseñados para comprobar su funcionamiento en producción?

### 2.2 Consistencia y Rigor Metodológico
- [ ] **C-01: Bidireccionalidad:** ¿Se verifica que la trazabilidad sea bidireccional, es decir, que se pueda rastrear tanto desde el requisito hacia el diseño y las pruebas (hacia adelante), como desde las pruebas y el diseño de vuelta hacia el requisito (hacia atrás)?
- [ ] **C-02: Ausencia de Ambigüedades (TBD):** ¿La matriz se encuentra libre de marcadores temporales o celdas con la leyenda "TBD" para todos los requerimientos que ya están en estado "Aprobado" y firmados?
- [ ] **C-03: Sincronización de Identificadores:** ¿Los códigos e identificadores de los requerimientos (`REQ-XX`), diagramas (`STD-XX`) y pruebas (`CP-XX`) coinciden exactamente con los nombres físicos de los archivos en sus respectivas carpetas?

### 2.3 Formato y Usabilidad
- [ ] **F-01: Wikilinks Interactivos:** ¿Todos los enlaces en la tabla de la matriz RTM están estructurados como wikilinks directos clickables de Obsidian hacia las notas físicas reales del vault, sin barras que descompongan la estructura de la tabla?
- [ ] **F-02: Segregación de Estados:** ¿Los requerimientos en estado "Pendiente" se encuentran claramente demarcados, reflejando su avance actual en la matriz sin comprometer la Línea Base aprobada?

---

## 3. Dictamen de Calidad SQA

*   **Documento Evaluado:** [Nombre y versión de la Matriz RTM evaluada]  
*   **Porcentaje de Conformidad:** [Número de ítems aprobados / 9 items] x 100%  
*   **Dictamen Final:** [APROBADO (Matriz Consistente) / RECHAZADO (Requiere Sincronización)]  

---

## 4. Control de Entregables Generados

A continuación se detalla la gobernanza del presente instrumento de checklist:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Checklist de Calidad de la Matriz RTM | CHK-RTM-VAL-XX | CMMI-DEV v2.0 REQM SP 1.4 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
