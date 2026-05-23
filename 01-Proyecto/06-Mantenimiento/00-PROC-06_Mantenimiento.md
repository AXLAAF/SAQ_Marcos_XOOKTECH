# Gestión de Mantenimiento de Sistemas -- XookTech
**Responsable:** Líder de Desarrollo e Implementación
**Entradas:** Manuales de Usuario y Sistema
**Salidas:** Plan de Soporte y Bitácora de Incidencias

**Área de proceso:** 06-Mantenimiento
**Nombre del proceso:** Soporte y Evolución del Sistema
**Notación:** NT: Nota Técnica.

---

## Proceso

### 1. Recepción y Clasificación
Toda solicitud de mantenimiento (Correctivo o Evolutivo) debe registrarse en el [[06-Mantenimiento/01-Ingenieria_Soporte/01-REG-01_Solicitudes_Mantenimiento|REG-01]]. Se clasifica según severidad (Crítico, Alto, Normal).

### 2. Análisis de Impacto (Python/Flask)
El **Analista de Gobernanza y Diseño** evalúa qué módulos de la arquitectura Flask u OpenCV se verán afectados. 
- **NT-1**: No se permite parchear código sin antes actualizar el [[03-Diseño/01-Ingenieria_Arquitectura/04-STD-07_Arquitectura_Python|STD-07]] si la lógica cambia significativamente.

### 3. Implementación y Pruebas de Regresión
Se aplica la corrección en una rama de hotfix. Se deben re-ejecutar los casos de prueba del módulo afectado en [[05-Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02]].

### 4. Cierre y Aceptación
Se notifica al cliente y se marca como cerrado tras confirmación.

---

## Referencias
- **ISO/IEC 14764**: Software Engineering — Maintenance.
- **SWEBOK v4**: Knowledge Area 5.