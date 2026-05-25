# Checklist de Calidad para Fichas de Requisitos Individuales (CHK-REQ)
**Responsable:** Analista de Control y Cambios  
**Entradas:** Ficha de Requerimiento individual (`REQ-XX.md`), Estándar de Ingeniería de Requisitos de XookTech y guías de calidad SQA.  
**Salidas:** Evaluación de conformidad del requerimiento y registro de validación de SQA bajo los atributos SWEBOK.  

---

## 1. Instrucciones de Uso

Este checklist técnico es el instrumento de verificación obligatoria ejecutado de forma independiente por el **Analista de Control y Cambios** para evaluar la calidad y completitud de cada ficha de requerimiento individual (`REQ-XX.md`) antes de autorizar su congelamiento en la Línea Base aprobada. Todos los criterios deben marcarse con una `[x]` solo si cumplen al 100%. La existencia de un solo ítem no conforme dicta el rechazo del requerimiento.

---

## 2. Criterios de Evaluación de Calidad

### 2.1 Atributos de Calidad del Requisito (SWEBOK)
- [ ] **R-01: Atomicidad:** ¿El requerimiento describe una única función o comportamiento técnico específico, evitando el uso de conjunciones coordinadas ("y", "o") que multipliquen su alcance?
- [ ] **R-02: Verificabilidad:** ¿El requerimiento está formulado de forma cuantitativa, medible y objetiva, evitando adverbios y términos ambiguos ("rápido", "fácil", "amigable", "eficiente")?
- [ ] **R-03: No Ambigüedad:** ¿Posee una sola interpretación posible y lógica para el Líder de Desarrollo y el Analista de Verificación y Pruebas?
- [ ] **R-04: Completitud:** ¿El requerimiento describe detalladamente tanto el flujo principal de éxito como los flujos de excepción y de manejo de errores?

### 2.2 Estructura y Estilo (Estándar XookTech ETVX)
- [ ] **E-01: Identificador Estructurado:** ¿Cuenta con un código de registro único e incremental (`REQ-XX`) de acuerdo con la nomenclatura del SGC?
- [ ] **E-02: Clasificación de Prioridad:** ¿Tiene asignada explícitamente su prioridad de negocio (Alta / Media / Baja)?
- [ ] **E-03: Fuente de Origen:** ¿Enlaza bidireccionalmente a la fuente primaria de solicitud del requerimiento (Contrato de Desarrollo o Solicitud de Cambio `CR-XXX`)?
- [ ] **E-04: Escenarios BDD:** ¿Los criterios de aceptación están descritos exhaustivamente mediante la notación estructurada `Dado / Cuando / Entonces`?
- [ ] **E-05: Reglas de Negocio:** ¿Las reglas de negocio técnicas (`RN-XX-XX`) están explícitamente numeradas, detalladas y asociadas al requerimiento?

### 2.3 Acotamiento y Manejo de Datos
- [ ] **M-01: Cotas de Entrada/Salida:** ¿Se definen límites de datos específicos (ej: peso máximo de archivos de 10 MB, formatos JPEG/PNG, dimensiones mínimas del canvas de 200x200px)?
- [ ] **M-02: Control de Errores:** ¿Se detalla la lógica de mitigación en caso de que ocurran fallas del sistema o desconexiones en caliente (ej. fallback del renderizador)?

---

## 3. Dictamen de Calidad SQA

*   **ID del Requerimiento Evaluado:** [REQ-XX]  
*   **Nombre del Requerimiento:** [Título de la ficha evaluada]  
*   **Porcentaje de Conformidad:** [Número de ítems aprobados / 11 items] x 100%  
*   **Dictamen Final SQA:** [CONFORME (Pase a Línea Base) / NO CONFORME (Retrabajo)]  

---

## 4. Control de Entregables Generados

A continuación se detalla la gobernanza del presente instrumento de checklist:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Checklist de Requisitos Individuales | CHK-REQ-VAL-XX | SWEBOK v4.0 & IEEE Std 830 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
