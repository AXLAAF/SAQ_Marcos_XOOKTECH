# Proceso de Diseño del Sistema — XookTech

**Código de Registro:** PROC-03-01  
**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Requisitos Aprobados (Fichas REQ BDD estables en 01-Aprobados), Casos de Uso, Código Fuente del Prototipo en Repositorio Git ([Marcos2 GitHub](https://github.com/Bigsami89/Marcos2)).  
**Salidas:** Diagrama de Componentes (STD-04), Flujo del Sistema (STD-05), Modelo de Datos (STD-06), Inventario de Módulos (STD-07), e Inconsistencias de Calidad (HALLAZGO-01).  
**Propósito:** Definir el procedimiento operativo estandarizado y sistemático para la ingeniería inversa, modelado de componentes, flujos dinámicos de peticiones, diseño del esquema relacional de catálogos y auditorías de paridad código-diseño, bajo el rigor del Aseguramiento de Calidad (SQA) y el Ciclo Deming (PDCA).

---

## Información Preliminar

Los documentos e insumos necesarios para la ejecución del proceso se detallan a continuación:

| Nombre del documento | Ubicación en el Vault |
| --- | --- |
| Matriz de Trazabilidad de Requisitos (RTM) | [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]] |
| Diagrama de Componentes del Sistema | [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/01-STD-04_Diagrama_Componentes|STD-04]] |
| Flujo del Sistema y Secuencia HTTP | [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/02-STD-05_Flujo_Sistema|STD-05]] |
| Modelo de Datos y Esquema Técnico | [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/03-STD-06_Modelo_Datos|STD-06]] |
| Arquitectura del Código Python | [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/04-STD-07_Arquitectura_Python|STD-07]] |
| Registro de Inconsistencia Tecnológica | [[09-Notes/03-Diseño-Preview/02-Calidad_Diseño/HALLAZGO-01_Inconsistencia_Tecnologica|HALLAZGO-01]] |

---

## Proceso

Este proceso se rige bajo las fases del Ciclo Deming (PDCA) para asegurar la mejora continua y el control de calidad en cada etapa.

---

### Fase 1: Planeación (Planear)

Esta fase consiste en la inspección física del repositorio y la preparación de los insumos necesarios de dependencias técnicas y del catálogo.

1. **Paso 1 o Inspección de dependencias:** El Analista de Gobernanza y Diseño clona o verifica el repositorio Git oficial del sistema (disponible en [Marcos2 GitHub](https://github.com/Bigsami89/Marcos2)) e inspecciona el archivo `requirements.txt` en la raíz del repositorio local para catalogar las versiones de las librerías base (Flask, OpenCV, Pillow) heredadas del prototipo.
2. **Paso 2 o Mapear estructura física:** Mapea e inventaría físicamente el árbol de directorios del código fuente (`static/`, `templates/`, `services/`) para comprender la modularidad de archivos.
3. **Paso 3 o Identificar constantes del catálogo:** Localiza en el código del backend (`app.py`) la definición en memoria de las constantes y dimensiones del catálogo de marcos.
4. **Paso 4 o Inicialización del Diseño:** Crea una nota borrador en el entorno de previsualización `09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/` por cada estándar técnico (`STD-04` a `STD-07`) y de calidad (`HALLAZGO-01`) que requiera actualización.
5. **Paso 5 o Registro de Línea Base de Requisitos:** Mapea bidireccionalmente los requerimientos de la Línea Base (`REQ-01` a `REQ-06`) que servirán de insumo directo para el diseño de interfaces y datos.

---

### Fase 2: Diseño y Modelado (Hacer)

Esta fase comprende el diseño y especificación física y lógica de todos los componentes, secuencias HTTP, y del modelo relacional del catálogo de marcos.

6. **Paso 6 o Modelar arquitectura de componentes:** El Analista de Gobernanza y Diseño diseña el diagrama de bloques estructurado de componentes en [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/01-STD-04_Diagrama_Componentes|STD-04]], separando físicamente el Cliente (HTML/CSS/Three.js), el Servidor Flask API, el Motor de Procesamiento (OpenCV) y Pillow.
7. **Paso 7 o Trazabilidad de Interfaces:** Define los puertos y protocolos HTTP de comunicación REST entre la interfaz del navegador y los endpoints del servidor Flask.
8. **Paso 8 o Mapear secuencia HTTP y flujo dinámico:** Diseña en el estándar [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/02-STD-05_Flujo_Sistema|STD-05]] los diagramas de secuencia Mermaid.js que detallan el ciclo de vida de las llamadas asíncronas para carga de fotos (`/upload`) y selección de marcos (`/process`).
9. **Paso 9 o Reconstruir esquema de datos:** Diseña el diagrama Entidad-Relación y el diccionario de datos físico en el estándar [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/03-STD-06_Modelo_Datos|STD-06]], especificando llaves primarias, tipos SQLite y constantes del catálogo.
10. **Paso 10 o Documentar lógica de conversión matemática:** Detalla en el modelo de datos las ecuaciones matemáticas y fórmulas de equivalencia que convierten las dimensiones físicas en centímetros a píxeles de renderizado en el canvas.

---

### Fase 3: Validación y Auditoría de Paridad (Verificar)

Esta fase comprende la realización de las revisiones cruzadas independientes de paridad código-diseño y la resolución de las no conformidades técnicas identificadas.

11. **Paso 11 o Inspección cruzada de paridad:** El Analista de Gobernanza y Diseño realiza una inspección cruzada para contrastar la arquitectura del código fuente real contra los diagramas técnicos de diseño mapeados.
12. **Paso 12 o Detección de desviaciones:** En caso de hallar diferencias (como uso de librerías no planificadas o inconsistencia en nombres de variables), el Analista de Gobernanza y Diseño, en coordinación independiente con el Analista de Control y Cambios, las documenta formalmente en el registro [[09-Notes/03-Diseño-Preview/02-Calidad_Diseño/HALLAZGO-01_Inconsistencia_Tecnologica|HALLAZGO-01]].
13. **Paso 13 o Corrección y retrabajo:** El Analista de Gobernanza y Diseño notifica las discrepancias de paridad al Líder de Desarrollo e Implementación para que aplique los cambios correctivos correspondientes y actualice el código fuente.
14. **Paso 14 o Re-auditoría SQA de paridad:** Una vez corregido el código, se ejecuta una segunda inspección de paridad para certificar que el software coincide al 100% con los diagramas de diseño.
15. **Paso 15 o Registro de Aprobación de Calidad:**
    * **Caso A o Conforme:** Si la ficha y los diagramas respetan el checklist de diseño al 100%, el Analista de Control y Cambios firma el dictamen de calidad en el registro REG-03-01, congelando el diseño.
    * **Caso B o No Conforme:** Si persisten desviaciones, regresa la ficha a la Fase 2 (Paso 6) en estado Pendiente para su corrección.

---

### Fase 4: Control de Configuración y Línea Base (Actuar)

Esta fase ejecuta la inyección oficial de los artefactos de diseño aprobados a la Línea Base del SGC y el control de calidad independiente por SQA.

16. **Paso 16 o Segregación Física de Diseño:** El Analista de Gobernanza y Diseño mueve físicamente los diagramas y estándares aprobados (`STD-04` a `STD-07`) a la carpeta de aprobados oficiales de la Fase 03.
17. **Paso 17 o Actualizar Matriz RTM de Diseño:** Sincroniza la Matriz de Trazabilidad RTM (STD-03) mapeando bidireccionalmente los requerimientos de la Fase 02 con los diagramas arquitectónicos de la Fase 03 y los Casos de Prueba de la Fase 05.
18. **Paso 18 o Publicación de Inventario de Módulos:** El Analista de Gobernanza y Diseño documenta y congela el inventario de módulos definitivo en el estándar [[09-Notes/03-Diseño-Preview/01-Ingenieria_Diseño/04-STD-07_Arquitectura_Python|STD-07]].
19. **Paso 19 o Aprobación SQA Digital:** El Analista de Control y Cambios aplica de forma independiente el checklist de diseño de SQA sobre el vault y autoriza digitalmente la línea base de diseño.
20. **Paso 20 o Derivación Operativa a Desarrollo:** El diseño congelado y certificado en la Línea Base se entrega formalmente al Líder de Desarrollo como orden de trabajo oficial (Fase 04) y base de control ante futuras Solicitudes de Cambio (Fase 07).

---

## Justificación de Mejoras

* **Fase de Planeación:** Mapear la arquitectura de dependencias físicas y del catálogo de forma temprana previene fallas de integración.
* **Fase de Modelado:** Diseñar la componentización cliente-servidor y flujos dinámicos HTTP mediante Mermaid.js provee una base visual atómica.
* **Fase de Validación y Auditoría:** La inspección cruzada independiente de paridad código-diseño y el registro formal en HALLAZGO-01 deslindan responsabilidades de SQA.
* **Fase de Control de Configuración:** La segregación física de los diagramas, la actualización de la RTM y la firma digital despersonalizada aseguran la estabilidad.

---

## Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Diseño de Software.

[2] Lewis, W. E. (2009). _Software Testing and Continuous Quality Improvement_. USA: Auerbach Publications. (Ciclos PDCA e Inspecciones de Diseño).

[3] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Infraestructura para la Prevención de Errores).

[4] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Independencia de Roles en Revisiones de Diseño).