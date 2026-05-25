# Proceso de Diseño del Sistema — XookTech
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Especificación de Requisitos y Casos de Uso
**Salidas:** Arquitectura de Componentes y Diseño de Base de Datos

**Área de proceso:** Diseño de Software  
**Nombre del proceso:** Ingeniería inversa y diseño de arquitectura de componentes  
**Basado en:** Metodología Deming (Ciclo PDCA: Planear, Hacer, Verificar, Actuar)  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.

|Nombre del documento|Ubicación|
|---|---|
|Matriz de Trazabilidad de Requisitos (RTM)|[[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]]|
|Diagrama de Componentes del Sistema|[[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes|STD-04]]|
|Flujo del Sistema y Secuencia HTTP|[[03-Diseño/01-Ingenieria_Arquitectura/02-STD-05_Flujo_Sistema|STD-05]]|
|Modelo de Datos y Esquema Técnico|[[03-Diseño/01-Ingenieria_Arquitectura/03-STD-06_Modelo_Datos|STD-06]]|
|Arquitectura del Código Python|[[03-Diseño/01-Ingenieria_Arquitectura/04-STD-07_Arquitectura_Python|STD-07]]|
|Registro de Inconsistencia Tecnológica|[[03-Diseño/02-Calidad_Revisiones/HALLAZGO-01_Inconsistencia_Tecnologica|HALLAZGO-01]]|

---

## Proceso

### 1. Mapear y modelar la arquitectura de componentes (Planear)

**Actualmente:**

- No existen diagramas ni especificaciones de la arquitectura física o lógica del sistema. Los desarrolladores deciden de forma independiente e informal qué carpetas crear y cómo conectar el servidor con el navegador web sobre la marcha del desarrollo.
- No se realiza una inspección previa de los directorios ni del stack tecnológico de los sistemas heredados a los que se aplica ingeniería inversa, provocando fallos inesperados de integración y compatibilidad de librerías.

**NT-1:** Diseñar software sin definir los componentes y sus interacciones de hardware/software genera sistemas monolíticos, acoplados y sumamente difíciles de mantener. El SWEBOK v4 (Área de Conocimiento de Diseño de Software) [1] especifica que el diseño de arquitectura es el primer paso de planificación técnica para mapear módulos, carpetas e interfaces de comunicación. Daniel Galin [3] sustenta que definir de forma sistemática la infraestructura y las dependencias de software previene errores críticos de integración al arranque. Se propone modelar visualmente la separación cliente-servidor a través de un diagrama de bloques estructurado.

**Propuesta:**

- El Analista de Gobernanza y Diseño realiza una inspección física del repositorio local y lista las carpetas (`static/`, `templates/`, `services/`) para identificar la arquitectura del código fuente heredado.
- Verifica versiones de librerías en `requirements.txt` y del archivo principal `app.py`.
- Construye un diagrama de bloques estructurado en el estándar [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes|STD-04 Diagrama de Componentes]], separando físicamente el Cliente (interfaz HTML/CSS/JS), el Servidor (Flask API), el Motor de Procesamiento (OpenCV) y las dependencias de renderizado (Pillow).

---

### 2. Modelar el flujo de datos y ciclo de vida de peticiones (Hacer)

**Actualmente:**

- Se asume que los datos fluyen de manera implícita entre el frontend y el backend. No se documenta la secuencia de las peticiones HTTP ni cómo interactúan las vistas con las rutas Flask y el motor de visión artificial.
- Esto provoca que el equipo de desarrollo no entienda el ciclo de vida de los datos ni el orden de ejecución, dando lugar a ineficiencias y cuellos de botella al procesar imágenes de alta resolución.

**NT-2:** La falta de modelado del comportamiento dinámico del sistema impide la verificación del rendimiento y la trazabilidad de llamadas HTTP. Lewis (2009) [2] y SWEBOK v4 [1] enfatizan que el modelado dinámico (diagramas de secuencia e interacción) es un requerimiento técnico indispensable para validar la lógica del sistema y el flujo de control antes de programar. Se propone documentar la secuencia de llamadas HTTP usando la notación Mermaid.js para el mapeo visual.

**Propuesta:**

- El Analista de Gobernanza y Diseño identifica los endpoints críticos en el código del servidor Flask (tales como `@app.route('/upload')` o `@app.route('/process')`).
- Sigue y documenta el camino completo de la llamada desde la petición HTTP POST de la interfaz web hasta la persistencia de imágenes y su procesamiento en el servidor de visión.
- Diagrama en [[03-Diseño/01-Ingenieria_Arquitectura/02-STD-05_Flujo_Sistema|STD-05 Flujo del Sistema]] un diagrama de secuencia en **Mermaid.js** detallando la interacción entre el Usuario, el Navegador, el Servidor Flask y los módulos OpenCV/Pillow, explicando qué ocurre con los datos en cada salto del flujo.

---

### 3. Reconstruir y modelar el esquema de datos del sistema (Verificar)

**Actualmente:**

- Las estructuras de datos de las entidades y catálogos de marcos se declaran de manera ad-hoc en memoria del servidor sin un diseño de base de datos o esquema técnico de datos estructurado.
- No hay una descripción semántica de los atributos ni de las relaciones entre las entidades (ej. cómo se calculan y equivalen las dimensiones en píxeles cargadas por el usuario con las dimensiones físicas reales del marco seleccionado).

**NT-3:** La inconsistencia o informalidad en el diseño de datos es la causa principal de fallos de redondeo y renderizado de imágenes. Daniel Galin [3] resalta que una especificación de datos rigurosa y documentada actúa como una medida preventiva fundamental contra defectos de cálculo. Se propone reconstruir por ingeniería inversa un esquema técnico formal de datos que asigne nombres reales de variables, tipos de datos específicos y equivalencias de negocio.

**Propuesta:**

- El Analista de Gobernanza y Diseño localiza las estructuras de datos que almacenan los catálogos en el backend (ejemplo: diccionarios o listas en memoria en `app.py`).
- Extrae el nombre exacto de cada variable (`width_px`, `texture_id`, `id`) y crea un modelo de datos formal que asigne tipos de datos y descripciones técnicas funcionales.
- Documenta en el estándar [[03-Diseño/01-Ingenieria_Arquitectura/03-STD-06_Modelo_Datos|STD-06 Modelo de Datos]] el esquema técnico, detallando la equivalencia y el cálculo entre píxeles y centímetros de los marcos.

---

### 4. Evaluar la paridad código-diseño e inspeccionar la arquitectura (Actuar)

**Actualmente:**

- La arquitectura documentada y el código real divergen rápidamente durante el proyecto. No se realiza ninguna inspección formal que certifique que la implementación respeta los diagramas de arquitectura aprobados.
- Las inconsistencias tecnológicas encontradas por el equipo de aseguramiento de calidad (SQA) no se reportan de forma formal ni se gestionan mediante acciones correctivas, perdiéndose la oportunidad de mejora continua.

**NT-4:** En un SGC robusto y profesional, cualquier falla o divergencia de diseño detectada debe retroalimentar y corregir de inmediato el proceso mediante el ciclo PDCA. Lewis (2009) [2] e IEEE 1028-2008 establecen que la inspección formal e independiente de paridad código-diseño es el mecanismo más efectivo para certificar la integridad de la arquitectura. Se propone realizar inspecciones formales independientes y registrar cualquier no conformidad en un registro SQA formal para su resolución obligatoria.

**Propuesta:**

- El Analista de Gobernanza y Diseño, en coordinación independiente con el Analista de Control y Cambios, realiza una revisión exhaustiva cruzando la arquitectura documentada contra el código fuente real.
- Si se encuentra alguna inconsistencia o desviación (ejemplo: uso de librerías no planificadas o inconsistencias de nombres), se registra formalmente en el artefacto de calidad [[03-Diseño/02-Calidad_Revisiones/HALLAZGO-01_Inconsistencia_Tecnologica|HALLAZGO-01 Inconsistencia Tecnológica]].
- Se notifica al Líder de Desarrollo e Implementación para que aplique los cambios correctivos correspondientes y se actualizan los diagramas técnicos.
- El Analista de Gobernanza y Diseño documenta el inventario de módulos definitivo en el estándar [[03-Diseño/01-Ingenieria_Arquitectura/04-STD-07_Arquitectura_Python|STD-07 Arquitectura Python]].

---

## Justificación de Mejoras

**NT-1 — Mapeo y Modelado de Arquitectura**  
Mapear la arquitectura de componentes antes de codificar previene problemas de integración. SWEBOK v4 [1] y Galin [3] establecen que delimitar interfaces de entrada/salida es básico para la mantenibilidad.

**NT-2 — Modelado de Flujo HTTP de Secuencia**  
El modelado dinámico HTTP documenta la interacción interactiva de llamadas, previniendo ineficiencias de backend. Lewis (2009) [2] sustenta el modelado de secuencias como filtro clave para la verificación del rendimiento.

**NT-3 — Ingeniería Inversa de Datos**  
El modelado formal del esquema de variables físicas del catálogo elimina defectos de redondeo y dimensiones al renderizar. Galin [3] promueve la especificación exacta de datos como medida de prevención de fallas de cálculo.

**NT-4 — Auditoría de Paridad Código-Diseño (PDCA)**  
Las inspecciones independientes de paridad de arquitectura certifican que el código implementado coincide con los diagramas de diseño. Lewis (2009) [2] e IEEE 1028-2008 recomiendan las revisiones por pares y auditorías en el ciclo Deming para retroalimentar la mejora.

---

## Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Diseño de Software.

[2] Lewis, W. E. (2009). _Software Testing and Continuous Quality Improvement_. USA: Auerbach Publications. (Ciclos PDCA e Inspecciones de Diseño).

[3] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Infraestructura para la Prevención de Errores).

[4] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Independencia de Roles en Revisiones de Diseño).

[5] Diagrama de Componentes. [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes|STD-04]]

[6] Flujo del Sistema. [[03-Diseño/01-Ingenieria_Arquitectura/02-STD-05_Flujo_Sistema|STD-05]]

[7] Modelo de Datos. [[03-Diseño/01-Ingenieria_Arquitectura/03-STD-06_Modelo_Datos|STD-06]]

[8] Arquitectura Python. [[03-Diseño/01-Ingenieria_Arquitectura/04-STD-07_Arquitectura_Python|STD-07]]

[9] Registro de Hallazgo SQA. [[03-Diseño/02-Calidad_Revisiones/HALLAZGO-01_Inconsistencia_Tecnologica|HALLAZGO-01]]