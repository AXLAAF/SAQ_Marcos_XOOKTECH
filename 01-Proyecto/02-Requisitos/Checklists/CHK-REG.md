# Checklist de Calidad para el Registro de Verificación (CHK-REG)
**Responsable:** Analista de Control y Cambios  
**Entradas:** Registro de Verificación de Requisitos (`REG-02-01_Verificacion_Requisitos.md`), Fichas de Requisitos y Checklists aplicados.  
**Salidas:** Dictamen de conformidad sobre la integridad y veracidad del registro de control SQA.  

---

## 1. Instrucciones de Uso

Este checklist es el instrumento técnico obligatorio para auditar la integridad y el rigor del **Registro de Verificación de Requisitos** (`REG-02-01_Verificacion_Requisitos.md`) en el SGC. El **Analista de Control y Cambios** debe ejecutar este control antes de cada entrega formal a fin de certificar que todos los registros de calidad son verídicos, completos y transparentes.

---

## 2. Criterios de Evaluación de Calidad

### 2.1 Coherencia e Integridad de la Auditoría SQA
- [ ] **R-01: Correspondencia Exacta:** ¿El registro incluye de forma unívoca a todos los requerimientos que han sido marcados con el estado "Aprobado" en la carpeta física oficial?
- [ ] **R-02: Registro de Evaluadores:** ¿Se detalla con precisión el nombre y el rol institucional despersonalizado del SQA que ejecutó cada evaluación (Analista de Control y Cambios)?
- [ ] **R-03: Registro Cronológico:** ¿Se cuenta con una fecha de evaluación explícita y coherente respecto al historial de desarrollo para cada entrada?
- [ ] **R-04: Trazabilidad del Instrumento:** ¿Se enlazan explícitamente las evidencias y los checklists técnicos utilizados (como `[[02-Requisitos/Checklists/CHK-REQ]]`) para sustentar la conformidad de cada requisito?

### 2.2 Gestión de No Conformidades y Acciones Correctivas
- [ ] **N-01: Documentación de Desvíos:** ¿Se describen explícitamente en la sección de hallazgos todas las no conformidades iniciales detectadas durante las inspecciones técnicas de calidad?
- [ ] **N-02: Evidencia de Acción Correctiva:** ¿Se registran formalmente las acciones tomadas para subsanar los desvíos (ej: adición de cotas numéricas, clarificación de reglas) y la posterior re-evaluación exitosa?
- [ ] **N-03: Dictamen Cuantitativo:** ¿Cada requerimiento tiene asociado un porcentaje cuantitativo real de conformidad, respaldando de forma objetiva la aprobación final de calidad (ej. `100.00% Conforme`)?

### 2.3 Formato y Reglas de XookTech v2.0
- [ ] **F-01: Ausencia de YAML/Firmas:** ¿El archivo del registro está libre de YAML frontmatter al inicio y no cuenta con firmas físicas o leyendas de generación personalizadas en sus últimas 5 líneas?
- [ ] **F-02: Enlaces Interactivos:** ¿Todos los identificadores de requisitos y checklists son wikilinks interactivos directos hacia las notas físicas reales correspondientes?

---

## 3. Dictamen de Calidad SQA

*   **Registro Evaluado:** [Nombre y versión del Registro de Verificación evaluado]  
*   **Porcentaje de Conformidad:** [Número de ítems aprobados / 9 items] x 100%  
*   **Dictamen Final:** [APROBADO (Registro Confiable) / RECHAZADO (Hallazgos Pendientes)]  

---

## 4. Control de Entregables Generados

A continuación se detalla la gobernanza del presente instrumento de checklist:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Checklist del Registro de Verificación | CHK-REG-VAL-XX | Galin 2004 & SWEBOK v4.0 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
