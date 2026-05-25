# Consulta de Calidad: Origen y Vinculación SQA de la Fase de Diseño

**Código de Registro:** NOT-09-03  
**Responsable:** Analista de Gobernanza y Diseño  
**Fecha de Elaboración:** 24 de Mayo de 2026  
**Entradas:** Minuta de alineación `MIN-09-01`, proceso original `03-Diseño/03-PROC-03_Diseño_Sistema.md`, repositorio Git oficial de Marcos2 y Matriz de Trazabilidad de Requisitos `STD-03`.  
**Salidas:** Nota de control técnico y remediación aplicada al SGC para certificar la consistencia del diseño.

---

## 1. Introducción y Contexto

Durante la revisión cruzada del preview de la **Fase 03 (Diseño)** bajo el estándar máster del SGC, el equipo de Auditoría de Calidad (liderado por Axel) identificó dos áreas de oportunidad críticas que requerían formalización:
1. **La Caja Negra de la Infraestructura Física:** El proceso describía la inspección de dependencias y de la estructura de archivos, pero no especificaba ni el enlace al repositorio Git de origen ni la ubicación física de `requirements.txt`.
2. **La Trazabilidad de Causalidad:** La necesidad de documentar con precisión cómo se vinculan conceptual y físicamente las fichas de requisitos de la **Fase 02** con los estándares técnicos de la **Fase 03**.

Esta nota de consultoría documenta la remediación oficial aplicada y los principios de diseño que rigen este vínculo.

---

## 2. Origen del Código Fuente y Dependencias

Para eliminar cualquier ambigüedad en el **Paso 1 o Inspección de dependencias**, se formalizó que la base física de ingeniería es el repositorio Git del prototipo.

### A. Repositorio Oficial y Localización
* **Repositorio Git Remoto:** `https://github.com/Bigsami89/Marcos2` (documentado en el archivo [[Contexto|Contexto.md]]).
* **Ubicación del Archivo de Dependencias:** El archivo `requirements.txt` se encuentra en la raíz del repositorio local una vez que ha sido clonado de la fuente oficial.

### B. Remediación en el Preview (`09-Notes/03-Diseño-Preview/`)
Se inyectaron los cambios correspondientes en los documentos operativos del preview para deslindar ambigüedades:
* **[[09-Notes/03-Diseño-Preview/03-PROC-03_Diseño_Sistema|03-PROC-03_Diseño_Sistema.md]]:** 
  * Se actualizó la sección de *Entradas* del proceso para incluir el repositorio remoto: `Código Fuente del Prototipo en Repositorio Git ([Marcos2 GitHub](https://github.com/Bigsami89/Marcos2))`.
  * Se reformuló el **Paso 1** (Fase de Planeación) para obligar a la clonación y verificación:
    > *"El Analista de Gobernanza y Diseño clona o verifica el repositorio Git oficial del sistema (disponible en [Marcos2 GitHub](https://github.com/Bigsami89/Marcos2)) e inspecciona el archivo `requirements.txt` en la raíz del repositorio local..."*
* **[[09-Notes/03-Diseño-Preview/00-MET-03_Plan_Metaproceso_Diseño|00-MET-03_Plan_Metaproceso_Diseño.md]]:**
  * Se añadieron el repositorio de código fuente y `requirements.txt` como *Insumo de Entrada* formal en la Actividad 1.
  * Se ajustó el paso correspondiente en la propuesta de la Actividad 1.

---

## 3. Vinculación y Trazabilidad Bidireccional con 02-Requisitos

La conexión entre la Fase 02 (Requisitos) y la Fase 03 (Diseño) se materializa en tres niveles de control de calidad:

### A. Relación de Causalidad Técnica
Ningún diagrama de diseño existe en el vacío; cada estándar técnico de la Fase 03 es la respuesta de ingeniería directa para resolver uno o más requerimientos de la Fase 02:

```
+------------------------------------------+       +------------------------------------------+
|          FASE 02: REQUISITOS             |       |            FASE 03: DISEÑO               |
+------------------------------------------+       +------------------------------------------+
|  REQ-01 Carga de Imagen                  | ====> |  STD-04 Diagrama de Componentes         |
|  REQ-07 Marcos Dobles                    |       |  (Arquitectura física Cliente/Servidor)  |
+------------------------------------------+       +------------------------------------------+
|  REQ-02 Previsualización Marco           | ====> |  STD-05 Flujo del Sistema (Mermaid)      |
|                                          |       |  (Ciclo dinámico HTTP /upload y /process)|
+------------------------------------------+       +------------------------------------------+
|  REQ-03 Generación Marcos 3D             | ====> |  STD-06 Modelo de Datos                  |
|  REQ-06 Datos Catálogo                   |       |  (Diccionario de datos y equivalencias)  |
+------------------------------------------+       +------------------------------------------+
|  REQ-04 Catálogo de Marcos               | ====> |  STD-07 Arquitectura Python              |
|  REQ-05 Filtrado Catálogo                |       |  (Inventario de módulos e instanciación) |
+------------------------------------------+       +------------------------------------------+
```

### B. El Registro en la Matriz de Trazabilidad RTM (`STD-03`)
El vínculo físico se formaliza matemáticamente en la **Matriz de Trazabilidad de Requisitos** (ubicada en [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|01-STD-03_Matriz_Trazabilidad.md]]).
Esta matriz asegura que el 100% de los requerimientos de la Línea Base tengan una contraparte de diseño aprobada, previniendo la acumulación de deuda de cobertura.

### C. Compuertas de Calidad (Entry & Exit Criteria)
* **Entry Criteria de Diseño:** Un requerimiento no puede ser diseñado en la Fase 03 si no cuenta con el estado "Aprobado" y su evidencia física en la subcarpeta `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/`.
* **Exit Criteria de Diseño:** El proceso de diseño no puede ser congelado ni promovido a Línea Base si el Analista de Control y Cambios no certifica que todos los enlaces bidireccionales en la Matriz RTM (`STD-03`) están al 100% completos y válidos.

---

## 4. Conclusión

Gracias al hallazgo detectado por el equipo de calidad, se eliminó la ambigüedad física del repositorio Git en la Fase 1 y se formalizó la cadena de causalidad técnica que vincula el análisis de negocio (Fase 02) con el diseño de software (Fase 03). Esto garantiza que la exposición interactiva del Obsidian cuente con una navegación impecable y con trazabilidad absoluta.
