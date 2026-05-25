# Checklist de Verificación de Diseño de Software

**Responsable:** Analista de Verificación y Pruebas  
**Entradas:** Documento de Descripción de Diseño (SDD), diagramas de arquitectura en Mermaid.js y Matriz RTM.  
**Salidas:** Evaluación de conformidad del diseño para liberar a Codificación.  

---

## Metadatos de la Revisión
| Campo | Valor |
|---|---|
| Documento revisado | |
| Versión del SDD | |
| Revisor SQA | |
| Fecha | |
| Resultado general | Aprobado / Rechazado |

---

## Instrucciones
Marcar cada criterio como:
* **Cumple** (C)
* **No cumple** (NC)
* **No aplica** (N/A)

Los elementos marcados como "No cumple" deben corregirse antes de aprobar la liberación a la fase de Codificación.

---

## 1. Estructura y Completitud del SDD

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| E-01 | ¿El SDD sigue la estructura de la plantilla oficial (`PLT-FOR_Plantilla_SDD.md`)? | | |
| E-02 | ¿Incluye las secciones de Introducción, Propósito, Alcance y Glosario? | | |
| E-03 | ¿Citó de forma correcta las referencias técnicas? | | |

---

## 2. Vista de Descomposición (Lógica)

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| D-01 | ¿Describe la descomposición del sistema en componentes y subsistemas? | | |
| D-02 | ¿Se identifican las capas de backend, frontend y persistencia? | | |
| D-03 | ¿El diagrama en Mermaid.js renderiza correctamente sin errores en Obsidian? | | |

---

## 3. Vista de Comportamiento Lógico (Secuencia)

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| C-01 | ¿El comportamiento dinámico se detalla mediante diagramas de secuencia? | | |
| C-02 | ¿Se describen tanto los flujos de éxito como los flujos de error con sus respuestas? | | |

---

## 4. Vista Física (Directorios)

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| F-01 | ¿El documento detalla la estructura física de archivos del repositorio? | | |
| F-02 | ¿Establece convenciones claras para la organización de carpetas y módulos? | | |

---

## 5. Vista de Datos (Persistencia)

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| A-01 | ¿Se especifican tipos de datos, llaves primarias, foráneas y restricciones? | | |
| A-02 | ¿El modelo propuesto cubre todos los datos requeridos por los requisitos? | | |

---

## 6. Interfaces and APIs

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| I-01 | ¿Se detallan firmas de funciones con tipos de datos de entrada y salida? | | |
| I-02 | ¿Se definen las rutas de API, métodos HTTP y códigos de respuesta? | | |

---

## 7. Trazabilidad del Diseño

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| T-01 | ¿Cada componente del diseño tiene un identificador único? | | |
| T-02 | ¿El 100% de los componentes están mapeados a sus requisitos en la Matriz RTM? | | |

---

## Hallazgos Detectados
| ID | Descripción | Acción Correctiva Requerida |
|---|---|---|
| | | |

---

## Dictamen General de Liberación
* **Aprobado** (0 no conformidades)
* **Rechazado** (1 o más no conformidades)

**Resultado:**  
**Firma:** Revisor SQA  
**Fecha:**  
