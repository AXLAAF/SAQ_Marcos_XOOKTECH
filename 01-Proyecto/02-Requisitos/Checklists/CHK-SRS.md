# Checklist de Calidad de la Especificación de Requisitos de Software (SRS)

**Responsable:** Analista de Requerimientos  
**Entradas:** Especificación de Requisitos de Software (SRS) redactada, casos de negocio y guías metodológicas de SQA.  
**Salidas:** Checklist de calidad ejecutado, dictamen formal de conformidad de requerimientos y notas de hallazgos bajo IEEE Std 830.  

---

## 1. Instrucciones de Uso

Este checklist técnico es el instrumento de control de calidad obligatorio que debe ser ejecutado por el Analista de Requerimientos sobre el documento unificado SRS antes de su liberación a desarrollo. Cada criterio debe ser evaluado exhaustivamente, marcando con una `[x]` solo si cumple al 100%. Cualquier no conformidad identificada bloquea la aprobación de la SRS y requiere reiniciar la fase de corrección.

---

## 2. Criterios de Evaluación de Calidad (IEEE Std 830-1998)

### 2.1 Correctitud (Correct)
- [ ] **C-01:** ¿Cada requerimiento mapea directamente una necesidad legítima del cliente sin inventar funcionalidades ficticias?
- [ ] **C-02:** ¿La SRS cuenta con la aprobación digital explícita del Product Owner validando su alcance?

### 2.2 Ausencia de Ambigüedad (Unambiguous)
- [ ] **UA-01:** ¿Cada requerimiento tiene una sola interpretación lógica posible para desarrollo y pruebas?
- [ ] **UA-02:** ¿Todos los requisitos funcionales están modelados con escenarios de aceptación explícitos en formato BDD (`Dado / Cuando / Entonces`)?
- [ ] **UA-03:** ¿Se definen límites precisos, parámetros y cotas numéricas (ej. formatos permitidos, dimensiones, pesos) evitando términos vagos como "rápido" o "intuitivo"?

### 2.3 Completitud (Complete)
- [ ] **CP-01:** ¿Están especificadas todas las funciones requeridas del sistema del Visualizador de Marcos?
- [ ] **CP-02:** ¿Se describen detalladamente las interfaces externas (interfaz gráfica del usuario e interfaz física de software)?
- [ ] **CP-03:** ¿Se definen explícitamente las restricciones del proyecto (stack tecnológico de Flask/OpenCV, compatibilidad en Linux y optimización de touchpad)?

### 2.4 Consistencia (Consistent)
- [ ] **CS-01:** ¿Todos los identificadores de requerimientos y flujos técnicos del sistema están libres de conflictos lógicos de nomenclatura?
- [ ] **CS-02:** ¿Se verifica que ningún requerimiento de interfaz o rendimiento contradiga las restricciones de negocio aprobadas?

### 2.5 Verificabilidad (Verifiable)
- [ ] **V-01:** ¿Todos los requerimientos están descritos de manera tal que se pueda diseñar un caso de prueba cuantitativo y medible para comprobarlos?
- [ ] **V-02:** ¿Existe una separación lógica clara entre los flujos funcionales del backend y los controles estéticos de la interfaz gráfica del cliente?

### 2.6 Rastreabilidad (Traceable)
- [ ] **T-01:** ¿Cada requisito cuenta con un identificador estructurado único (`REQ-XX`) e inalterable?
- [ ] **T-02:** ¿El 100% de los requisitos se encuentran correctamente mapeados en la Matriz de Trazabilidad RTM (`01-STD-03_Matriz_Trazabilidad.md`)?

---

## 3. Dictamen de Calidad SQA

*   **Documento Evaluado:** [Nombre y versión de la SRS evaluada]  
*   **Porcentaje de Conformidad:** [Número de ítems aprobados / Total de ítems] x 100%  
*   **Dictamen Final:** [APROBADO / RECHAZADO]  

---

## 4. Control de Entregables Generados

A continuación se detalla la gobernanza del presente instrumento de checklist:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Checklist de Calidad de SRS | CHK-SRS-VAL-XX | IEEE Std 830-1998 | [Estado del documento] |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
