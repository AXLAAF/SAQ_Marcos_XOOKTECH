# CL-02: Checklist de Verificacion de Requerimientos
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Estándares ETVX y Gobernanza
**Salidas:** Vault de Obsidian Auditado y Coherente

---

> Use este checklist para validar cada archivo `REQ-XX_Nombre` antes de enviarlo a inspeccion formal en el [[05-Revisiones e inspecciones/01-Ingenieria_Control/05-PROC-05.2_Inspecciones|PROC-09 Inspecciones]]. Un requerimiento solo es valido si cumple con el 100% de estos criterios.

## 1. Atributos de Calidad (SWEBOK)
- [ ] **Atomico**: ¿El requerimiento describe una unica funcionalidad? (No debe contener "y", "o" que dividan la logica).
- [ ] **Verificable**: ¿Existe una forma objetiva de probar si se cumplio? (Evitar palabras como "rapido", "facil", "amigable").
- [ ] **No Ambiguo**: ¿Tiene una sola interpretacion posible para un desarrollador y un tester?
- [ ] **Completo**: ¿Contiene flujos de excepcion y reglas de negocio cuantificadas?

## 2. Estructura Formal (Plantilla ETVX)
- [ ] **Identificador**: ¿Tiene un ID unico (REQ-XX)?
- [ ] **Prioridad**: ¿Esta clasificada (Alta/Media/Baja)?
- [ ] **Trazabilidad**: ¿Enlaza a la fuente original (Contrato/Minuta)?
- [ ] **Criterios BDD**: ¿Los escenarios Dado/Cuando/Entonces cubren el flujo principal?
- [ ] **Reglas de Negocio**: ¿Las RN-XX-XX estan claramente listadas y numeradas?

## 3. Manejo de Errores
- [ ] **Excepciones**: ¿Se define que pasa si falla la red o el servidor?
- [ ] **Validaciones**: ¿Se definen limites de datos (ej. "max 10MB", "min 200x200px")?

---
**Resultado de la Evaluacion:**
- **Requerimiento:** [ID del REQ]
- **Evaluador:** [Nombre]
- **Fecha:** [Fecha]
- **Estado:** [Aprobado / Requiere Retrabajo]