# Proceso de Soporte y Mantenimiento — XookTech
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Reportes de Error del Cliente y Solicitudes de Mejora
**Salidas:** Módulos de Código Corregidos y Bitácora de Soporte

**Área de proceso:** Soporte e Ingeniería de Software  
**Nombre del proceso:** Soporte técnico y mantenimiento del sistema  
**Basado en:** Metodología Deming (Ciclo PDCA: Planear, Hacer, Verificar, Actuar)  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.

|Nombre del documento|Ubicación|
|---|---|
|Registro de Solicitudes de Mantenimiento|[[08-Mantenimiento/01-Ingenieria_Soporte/01-REG-01_Solicitudes_Mantenimiento|REG-01]]|
|Registro de Errores Reportados|[[08-Mantenimiento/01-Ingenieria_Soporte/02-REG-02_Errores_Reportados|REG-02]]|
|Formato de Cotización de Cambios|[[08-Mantenimiento/01-Ingenieria_Soporte/01-FOR-01_Cotizacion_Cambios|FOR-01]]|
|Plan Maestro de Pruebas de Regresión|[[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02]]|
|Dashboard de Calidad|[[05-Revisiones e inspecciones/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08]]|

---

## Proceso

### 1. Recepción, registro y clasificación de incidencias (Planear)

**Actualmente:**

- Los clientes o usuarios finales reportan problemas lógicos o solicitudes de mejora de palabra, mediante llamadas directas no programadas o chats dispersos a los desarrolladores del prototipo.
- No existe una bitácora única centralizada ni se categorizan los reportes por severidad, lo que ocasiona que los fallos críticos de Flask o de OpenCV no se atiendan de manera oportuna ni con la debida prioridad técnica.

**NT-1:** Recibir incidentes de soporte de palabra sin documentarlos en una bitácora formal destruye la gobernanza de SQA. Conforme al estándar internacional ISO/IEC 14764 [5], todo proceso de mantenimiento de software profesional exige un canal estructurado y centralizado para recibir, registrar, categorizar (Correctivo, Adaptativo, Evolutivo, Preventivo) y priorizar de forma unívoca cada incidente post-entrega. G. O. Regan (2002) [3] sostiene que la clasificación sistemática de incidentes permite evaluar el comportamiento operacional y planificar con precisión el soporte. Se propone centralizar todo reporte en la bitácora de soporte.

**Propuesta:**

- El Analista de Gobernanza y Diseño recibe las solicitudes de soporte e incidencias técnicas a través de los canales de comunicación de la empresa.
- Registra inmediatamente el reporte en el [[08-Mantenimiento/01-Ingenieria_Soporte/01-REG-01_Solicitudes_Mantenimiento|REG-01 Registro de Solicitudes de Mantenimiento]] o en el [[08-Mantenimiento/01-Ingenieria_Soporte/02-REG-02_Errores_Reportados|REG-02 Registro de Errores Reportados]].
- Asigna un folio único estructurado, el tipo de mantenimiento requerido (Correctivo, Adaptativo, Evolutivo o Preventivo) y la prioridad del incidente (Alta, Media, Baja).

---

### 2. Análisis de impacto y cotización técnica de cambios (Hacer)

**Actualmente:**

- El equipo técnico modifica o "parchea" el código fuente directamente en producción sin realizar previamente un análisis formal de qué dependencias o módulos de la arquitectura Flask u OpenCV/Pillow se verán afectados.
- No se realiza una estimación de esfuerzo o tiempo, ni se elabora una cotización técnica que resguarde y formalice el compromiso comercial ante el Product Owner antes de aplicar el cambio.

**NT-2:** Parchear código fuente en producción sin un análisis sistemático de su impacto en la arquitectura de componentes y base de datos produce fallos laterales catastróficos e inconsistencias de diseño. El SWEBOK v4 (Mantenimiento de Software) [1] y Daniel Galin [4] señalan que el análisis de impacto técnico y la cotización de esfuerzo son controles obligatorios para mitigar riesgos antes de realizar cualquier cambio sobre la Línea Base estable. Se propone realizar un walkthrough de diseño previo y emitir la cotización del cambio.

**Propuesta:**

- El Analista de Gobernanza y Diseño analiza qué módulos del prototipo Flask o del motor OpenCV/Pillow se verán afectados por el cambio propuesto.
- Verifica que la modificación sea viable y no rompa los estándares de diseño técnico y bases de datos (`STD-04` a `STD-07`).
- Utiliza el formato [[08-Mantenimiento/01-Ingenieria_Soporte/01-FOR-01_Cotizacion_Cambios|FOR-01 Cotización de Cambios]] para estimar detalladamente el esfuerzo en horas y costo técnico.
- Obtiene la confirmación formal por escrito del Product Owner antes de autorizar la codificación del cambio en el repositorio Git.

---

### 3. Implementación del cambio y pruebas de regresión (Verificar)

**Actualmente:**

- Las correcciones o modificaciones se aplican en la rama principal sin realizar pruebas exhaustivas de regresión, asumiendo empíricamente que al resolver el error no se afectó ninguna otra funcionalidad del sistema.
- Esto genera defectos de regresión graves en producción, donde componentes estables (como la previsualización interactiva o el filtrado de catálogo de marcos) se rompen de forma imprevista por cambios colaterales.

**NT-3:** Modificar software heredado sin re-ejecutar pruebas completas expone al sistema a defectos de regresión no deseados en producción. William E. Lewis (2009) [2] establece que las Pruebas de Regresión (Regression Testing) son indispensables tras cualquier modificación correctiva o evolutiva del software para garantizar la estabilidad operativa. Se propone implementar el cambio en una rama aislada de Hotfix y re-ejecutar los casos de prueba de regresión pertinentes del Plan Maestro.

**Propuesta:**

- El Líder de Desarrollo e Implementación crea una rama de hotfix aislada en el repositorio Git (ejemplo: `hotfix/REG-06-01-correccion-zoom`).
- Implementa la corrección técnica apegándose al estándar de codificación.
- El Analista de Verificación y Pruebas re-ejecuta de inmediato los Casos de Prueba (CP-XXX) del módulo afectado y de los módulos relacionados detallados en el [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan de Pruebas]], verificando que no existan no conformidades.

---

### 4. Liberación, actualización de Línea Base y mejora continua (Actuar)

**Actualmente:**

- Una vez corregido el problema, el desarrollador integra los cambios directamente a la rama principal de producción.
- No se actualizan los diagramas de arquitectura ni el inventario de módulos de la documentación técnica del sistema, perdiéndose el historial de incidentes y lecciones aprendidas.

**NT-4:** En un SGC robusto y conforme al ciclo PDCA, la liberación de soporte debe actualizar formalmente los entregables de configuración y retroalimentar el Dashboard de Calidad. CMMI-DEV v1.3 (área de proceso Gestión de Configuración - CM) exige documentar y versionar todo cambio realizado sobre la Línea Base estable. Se propone registrar el cierre formal en la bitácora de soporte y actualizar los diagramas y el Dashboard de Calidad.

**Propuesta:**

- Una vez certificadas las pruebas de regresión, el Líder de Desarrollo e Implementación integra la rama de hotfix a la rama principal `main` y despliega la actualización.
- El Analista de Gobernanza y Diseño actualiza de ser necesario los diagramas técnicos modificados y el inventario de módulos.
- El Analista de Control y Cambios registra el cierre del incidente en el [[08-Mantenimiento/01-Ingenieria_Soporte/01-REG-01_Solicitudes_Mantenimiento|REG-01]] e incrementa las métricas de calidad en el [[05-Revisiones e inspecciones/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08 Dashboard de Calidad]], cerrando formalmente el ciclo Deming.

---

## Justificación de Mejoras

**NT-1 — Registro y Clasificación de Soporte**  
Registrar los incidentes evita retrasos y desorganización de servicio. ISO/IEC 14764 [5] y Regan (2002) [3] establecen que la clasificación formal es vital para planificar el soporte post-entrega.

**NT-2 — Análisis de Impacto y Cotización**  
Evaluar las dependencias técnicas de la arquitectura Flask/OpenCV antes de codificar previene defectos laterales. SWEBOK v4 [1] y Galin [4] exigen el análisis y estimación previos de los cambios.

**NT-3 — Pruebas de Regresión en Hotfix**  
La re-ejecución del Plan de Pruebas tras cualquier modificación asegura que los componentes estables permanezcan funcionales. Lewis (2009) [2] promueve las pruebas de regresión como un control indispensable del SGC.

**NT-4 — Gestión de la Configuración y Cierre (PDCA)**  
Versionar los diagramas modificados y actualizar las métricas en el Dashboard de Calidad (Ciclo PDCA) alimenta de forma continua la calidad de software conforme a CMMI-DEV.

---

## Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Mantenimiento de Software.

[2] Lewis, W. E. (2009). _Software Testing and Continuous Quality Improvement_. USA: Auerbach Publications. (Pruebas de Regresión y Soporte).

[3] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Estructura de Servicio y Roles SQA).

[4] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Gobernanza de Mantenimiento e Infraestructura).

[5] ISO/IEC 14764:2006. _Ingeniería de Software — Procesos del Ciclo de Vida del Software — Mantenimiento_. ISO/IEEE.

[6] Registro de Solicitudes. [[08-Mantenimiento/01-Ingenieria_Soporte/01-REG-01_Solicitudes_Mantenimiento|REG-01]]

[7] Registro de Errores. [[08-Mantenimiento/01-Ingenieria_Soporte/02-REG-02_Errores_Reportados|REG-02]]

[8] Cotización de Cambios. [[08-Mantenimiento/01-Ingenieria_Soporte/01-FOR-01_Cotizacion_Cambios|FOR-01]]