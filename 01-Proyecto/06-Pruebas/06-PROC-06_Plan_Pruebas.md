# Proceso de Planificación y Ejecución de Pruebas — XookTech
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

**Área de proceso:** Planificación y Ejecución de Pruebas  
**Nombre del proceso:** Planificación, diseño y ejecución de pruebas de software  
**Basado en:** Metodología Deming (Ciclo PDCA: Planear, Hacer, Verificar, Actuar)  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.

|Nombre del documento|Ubicación|
|---|---|
|Matriz de Trazabilidad de Requisitos (RTM)|[[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]]|
|Plan Maestro de Pruebas|[[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02]]|
|Registro de Defectos|[[05-Control de cambios/02-Calidad_Control/02-REG-03_Registro_Defectos|REG-03]]|
|Caso de Prueba CP-01 (Carga JPG Válida)|[[06-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/01-CP-01_JPG_valida|CP-01]]|
|Caso de Prueba CP-08 (Marco Simple)|[[06-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/01-CP-08_Marco_simple|CP-08]]|
|Reporte de Inspección de Plan de Pruebas|[[05-Control de cambios/02-Calidad_Control/06-INS-02_Inspeccion_Plan_Pruebas|INS-02]]|

---

## Proceso

### 1. Diseñar y planificar los casos de prueba (Planear)

**Actualmente:**

- No se diseñaban casos de prueba ni se planificaban las validaciones. El desarrollador o el validador probaba de forma aleatoria e informal ("al aire") el prototipo, perdiéndose la cobertura de casos de borde críticos (MIME types, imágenes de gran tamaño o fallas de red).
- No existía una relación clara entre los requisitos aprobados y lo que se validaba en el software, provocando vacíos de cobertura funcionales graves.

**NT-1:** Probar sin una planificación formal basada en los requisitos imposibilita la verificación objetiva, la cobertura completa y la repetibilidad de las pruebas. El SWEBOK v4 (Área de Pruebas de Software) [1] y William E. Lewis (2009) [2] establecen que las pruebas de software deben planificarse con anticipación, diseñando casos de prueba estructurados y priorizados que cubran Happy Paths, límites y excepciones asociados a los requisitos aprobados. Se propone diseñar el Plan Maestro de Pruebas e individualizar los casos en base a los criterios BDD de los requerimientos.

**Propuesta:**

- El Analista de Verificación y Pruebas revisa la Línea Base de requisitos aprobada en `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/` y sus Criterios de Aceptación BDD.
- Elabora de forma estructurada el [[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|Plan Maestro de Pruebas (PLAN-02)]] para definir la estrategia de validación en los 4 módulos (Carga, Catálogo, Previsualización y Pantalla Secundaria).
- Diseña y redacta los 15 Casos de Prueba (de `CP-01` a `CP-15`), detallando para cada uno las Precondiciones, Pasos de Ejecución y Resultados Esperados en sus respectivos archivos markdown en Obsidian (ej. [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/01-CP-01_JPG_valida|CP-01 JPG Valida]] o [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/01-CP-08_Marco_simple|CP-08 Marco Simple]]).

---

### 2. Configurar el entorno y preparar los datos de prueba (Hacer)

**Actualmente:**

- Las pruebas se ejecutaban directamente sobre la marcha en entornos inestables de desarrollo sin contar con un set de datos de prueba predefinido y documentado.
- Esto provocaba que no se pudieran reproducir de forma consistente los fallos de detección de OpenCV o los errores de renderizado de Pillow, dificultando el aislamiento y corrección del código.

**NT-2:** La inconsistencia o informalidad en el entorno de pruebas y datos invalida los resultados de la verificación. Lewis (2009) [2] e IEEE 829 recomiendan que todo entorno de pruebas esté controlado, aislado y con datos de entrada específicos (imágenes reales con dimensiones conocidas) para certificar la repetibilidad de la prueba. Se propone un entorno controlado de ejecución de Flask API, OpenCV y Pillow locales con sets de datos de prueba específicos.

**Propuesta:**

- El Analista de Verificación y Pruebas prepara el entorno local del prototipo en Flask sobre el stack tecnológico de desarrollo (CachyOS).
- Crea una carpeta de assets de prueba con imágenes base de resoluciones y formatos conocidos (JPG válidos de 5 MB, imágenes gigantescas de 15 MB, archivos MIME no válidos como PDF).
- Configura el entorno de logs del servidor para registrar de manera precisa los tiempos de respuesta y consumo de memoria.

---

### 3. Ejecutar las pruebas e inspeccionar resultados (Verificar)

**Actualmente:**

- Las pruebas las ejecutaba de forma manual e informal el mismo desarrollador que escribió el código real.
- No existía un registro de los resultados ni se capturaban los logs de error del servidor, lo que impedía que los defectos se pudieran depurar con rapidez.

**NT-3:** La revisión del propio código tiene un sesgo cognitivo que limita la detección de fallos. El estándar IEEE 1028-2008 de revisiones e inspecciones y Daniel Galin [4] exigen la **independencia de criterio** en las actividades de V&V, requiriendo que la ejecución de pruebas sea ejecutada o inspeccionada formalmente por un rol independiente (Revisión por Pares - Peer Review). Se propone la ejecución de pruebas por pares con captura de evidencias de logs y tiempos.

**Propuesta:**

- El Analista de Verificación y Pruebas ejecuta de forma secuencial los 15 casos de prueba siguiendo las instrucciones de ejecución.
- Registra minuciosamente la salida obtenida y captura evidencias objetivas (logs de terminal, capturas de pantalla de la interfaz Flask renderizada).
- Coordina una Revisión por Pares (Peer Review) para auditar y certificar que la ejecución sea transparente e independiente.

---

### 4. Registrar defectos y retroalimentar el proceso (Actuar)

**Actualmente:**

- Los fallos encontrados se informaban de palabra o por chats informales a los desarrolladores.
- No se llevaba una estadística de los errores encontrados, provocando que los mismos defectos lógicos en OpenCV o Pillow recurrieran en cada sprint sin resolverse de fondo.

**NT-4:** La falta de documentación sistemática de defectos anula el ciclo de mejora continua. CMMI-DEV v1.3 y William E. Lewis (2009) [2] enfatizan que el Registro de Defectos es la herramienta vital de SQA que alimenta dinámicamente el ciclo PDCA para corregir y actualizar los estándares de codificación e ingeniería, previniendo la reincidencia. Se propone el registro formal de defectos en una matriz centralizada.

**Propuesta:**

- El Analista de Verificación y Pruebas registra de inmediato cualquier discrepancia o fallo detectado en el [[05-Control de cambios/02-Calidad_Control/02-REG-03_Registro_Defectos|REG-03 Registro de Defectos]] a cargo del *Analista de Control y Cambios*.
- Asigna al defecto un folio (DEF-XXX), prioridad y descripción detallada del error lógico y paso de reproducción.
- Retroalimenta al *Líder de Desarrollo e Implementación* para la corrección inmediata en código y coordina con el *Analista de Control y Cambios* para evaluar acciones preventivas y actualizar los checklists si es necesario.

---

## Justificación de Mejoras

**NT-1 — Planificación y Casos de Prueba**  
La planificación sistemática evita vacíos de cobertura funcional y asegura la repetibilidad. SWEBOK v4 [1] y Lewis (2009) [2] establecen que el diseño estructurado de casos de prueba es básico para la verificación objetiva.

**NT-2 — Entorno de Pruebas Controlado**  
Configurar un entorno y set de datos aislados garantiza resultados consistentes y reproducibles. Lewis (2009) [2] e IEEE 829 recomiendan datos de entrada conocidos (JPG, PNG) para aislar fallos en OpenCV/Pillow.

**NT-3 — Ejecución Independiente y Peer Review**  
La revisión por pares elimina el sesgo cognitivo del desarrollador. IEEE 1028-2008 y Galin [4] exigen la independencia de criterio en verificación y validación (V&V).

**NT-4 — Registro de Defectos y Mejora Continua (PDCA)**  
El registro formal (DEF-XXX) retroalimenta dinámicamente la codificación para prevenir recurrencias (Ciclo PDCA). CMMI-DEV y Lewis (2009) [2] lo catalogan como el motor de la mejora continua del SGC.

---

## Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Pruebas de Software.

[2] Lewis, W. E. (2009). _Software Testing and Continuous Quality Improvement_. USA: Auerbach Publications. (Rigor de Pruebas e Integración del Ciclo PDCA).

[3] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Estructura Organizativa de Calidad e Independencia).

[4] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Calidad Contractual e Infraestructura).

[5] Matriz de Trazabilidad de Requisitos (RTM). [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]]

[6] Plan Maestro de Pruebas. [[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02]]

[7] Registro de Defectos de SQA. [[05-Control de cambios/02-Calidad_Control/02-REG-03_Registro_Defectos|REG-03]]

[8] Caso de Prueba CP-01 (Carga JPG). [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/01-CP-01_JPG_valida|CP-01]]

[9] Caso de Prueba CP-08 (Marco Simple). [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/01-CP-08_Marco_simple|CP-08]]

[10] Reporte de Inspección de Pruebas. [[05-Control de cambios/02-Calidad_Control/06-INS-02_Inspeccion_Plan_Pruebas|INS-02]]