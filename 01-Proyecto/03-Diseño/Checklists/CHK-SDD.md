# Checklist de Calidad de la Descripción de Diseño de Software (SDD)

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Documento de Descripción de Diseño de Software (SDD) redactado, diagramas del sistema en Mermaid.js y directrices metodológicas de SQA.  
**Salidas:** Checklist de calidad ejecutado, dictamen formal de conformidad de arquitectura de software y notas de hallazgos bajo IEEE Std 1016.  

---

## 1. Instrucciones de Uso

Este checklist técnico es el instrumento de control de calidad obligatorio que debe ser ejecutado por el Analista de Gobernanza y Diseño sobre el documento unificado SDD antes de su liberación formal a codificación. Cada criterio debe ser evaluado exhaustivamente, marcando con una `[x]` solo si cumple al 100%. Cualquier no conformidad detectada bloquea la aprobación de la arquitectura de software.

---

## 2. Criterios de Evaluación de Calidad (IEEE Std 1016-2009)

### 2.1 Punto de Vista de Descomposición (Decomposition Viewpoint)
- [ ] **DES-01:** ¿El diseño lógico describe con precisión la división física y de software en componentes independientes?
- [ ] **DES-02:** ¿Se identifican claramente los subsistemas de Backend (Flask/OpenCV) y Frontend (Interfaz Cliente), delimitando sus responsabilidades técnicas?

### 2.2 Punto de Vista de Comportamiento Lógico (Logical Viewpoint)
- [ ] **LOG-01:** ¿El comportamiento del sistema está modelado a través de diagramas lógicos dinámicos que muestran la interacción temporal de los componentes de software?
- [ ] **LOG-02:** ¿Se describen claramente las transiciones de estados del Visualizador de Marcos y las rutinas de procesamiento gráfico ante entradas válidas e inválidas?

### 2.3 Punto de Vista Físico (Physical Viewpoint)
- [ ] **FIS-01:** ¿El documento detalla con exactitud el esqueleto de directorios del proyecto Python y la ubicación de archivos críticos en el disco?
- [ ] **FIS-02:** ¿Se establecen pautas claras sobre el despliegue del software y compatibilidad con Linux (ASUS Vivobook 14 X1404ZA/CachyOS)?

### 2.4 Punto de Vista de Datos (Data Viewpoint)
- [ ] **DAT-01:** ¿Están descritos con precisión los tipos de datos, llaves primarias y esquemas JSON o tablas SQLite del sistema?
- [ ] **DAT-02:** ¿Se verifica la consistencia de los datos entre componentes, evitando redundancias o esquemas divergentes?

### 2.5 Interfaces de Componentes y APIs
- [ ] **INT-01:** ¿Se especifican con exactitud matemática las signaturas de funciones críticas de Flask y procesamiento con OpenCV?
- [ ] **INT-02:** ¿Están delimitados con claridad los parámetros de entrada y salida, tipos de retorno y respuestas HTTP de error del backend?

### 2.6 Rastreabilidad de la Arquitectura
- [ ] **TR-01:** ¿Cada componente lógico o subsistema del diseño de software cuenta con un identificador unificado e inalterable?
- [ ] **TR-02:** ¿El 100% de los elementos de diseño están directamente trazados a sus requisitos relacionados en la Matriz RTM (`01-STD-03_Matriz_Trazabilidad.md`)?

---

## 3. Dictamen de Calidad SQA

*   **Documento Evaluado:** [Nombre y versión de la especificación SDD evaluada]  
*   **Porcentaje de Conformidad:** [Número de ítems aprobados / Total de ítems] x 100%  
*   **Dictamen Final:** [APROBADO / RECHAZADO]  

---

## 4. Control de Entregables Generados

A continuación se detalla la gobernanza del presente instrumento de checklist:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Checklist de Calidad de SDD | CHK-SDD-VAL-XX | IEEE Std 1016-2009 | [Estado del documento] |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
