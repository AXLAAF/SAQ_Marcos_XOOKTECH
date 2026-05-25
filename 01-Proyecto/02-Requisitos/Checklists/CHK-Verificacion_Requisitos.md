# Checklist de Verificación de Requisitos de Software

**Responsable:** Analista de Control y Cambios  
**Entradas:** Fichas de requisitos (`REQ-XX.md`), Especificación de Requisitos (SRS), Matriz RTM y Registro SQA.  
**Salidas:** Evaluación de conformidad de los requisitos para liberar a Diseño.  

---

## Metadatos de la Revisión
| Campo | Valor |
|---|---|
| Documento revisado | |
| Evaluador (Rol) | Analista de Control y Cambios |
| Fecha | |
| Resultado general | Aprobado / Rechazado |

---

## Instrucciones
Marcar cada criterio como:
* **Cumple** (C)
* **No cumple** (NC)
* **No aplica** (N/A)

Los elementos marcados como "No cumple" deben corregirse antes de aprobar la liberación a la fase de Diseño.

---

## Sección A: Verificación del Documento de Especificación (SRS)

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| C-01 | ¿Cada requisito responde a una necesidad del cliente? | | |
| C-02 | ¿Cuenta con la firma o aprobación digital del Product Owner? | | |
| C-03 | ¿Cada requisito tiene una interpretación clara y única? | | |
| C-04 | ¿Los requisitos funcionales están descritos con escenarios BDD (Dado/Cuando/Entonces)? | | |
| C-05 | ¿Se definen límites numéricos (formatos, dimensiones, pesos) evitando adjetivos ambiguos? | | |
| C-06 | ¿Describe todas las funciones del Visualizador de Marcos? | | |
| C-07 | ¿Detalla las interfaces de usuario y de software? | | |
| C-08 | ¿Respeta las restricciones tecnológicas (Flask, OpenCV, Linux)? | | |
| C-09 | ¿Los identificadores de requisitos están libres de duplicados? | | |
| C-10 | ¿Cada requisito es medible y se puede probar? | | |
| C-11 | ¿Cada requisito tiene un código único (`REQ-XX`)? | | |
| C-12 | ¿El 100% de los requisitos están mapeados en la Matriz RTM? | | |

---

## Sección B: Verificación de Requisitos Individuales

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| R-01 | **Atomicidad:** ¿El requerimiento describe una sola función específica? | | |
| R-02 | **Verificabilidad:** ¿Está escrito sin adjetivos subjetivos ("rápido", "fácil", "eficiente")? | | |
| R-03 | **Completitud:** ¿Incluye el flujo principal de éxito y los flujos alternos o de error? | | |
| R-04 | **Prioridad:** ¿Tiene asignada prioridad (Alta, Media, Baja)? | | |
| R-05 | **Origen:** ¿Enlaza al documento de origen (Contrato o Solicitud de Cambio `CR-XXX`)? | | |
| R-06 | **Reglas de Negocio:** ¿Detalla y numera las reglas técnicas aplicables? | | |
| R-07 | **Límites:** ¿Especifica valores límite (ej. tamaño máximo de archivos 10 MB)? | | |

---

## Sección C: Verificación de la Matriz de Trazabilidad RTM

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| M-01 | ¿La matriz incluye el 100% de los requisitos de la línea base? | | |
| M-02 | ¿Cada requisito está enlazado a su origen (Contrato o `CR-XXX`)? | | |
| M-03 | ¿Cada requisito está enlazado a su sección en el diseño de software? | | |
| M-04 | ¿Cada requisito está enlazado a su caso de prueba correspondiente? | | |
| M-05 | ¿Los enlaces en la tabla funcionan correctamente y no tienen marcadores "TBD"? | | |

---

## D: Verificación del Registro SQA

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| S-01 | ¿El registro incluye todos los requisitos aprobados de la carpeta física? | | |
| S-02 | ¿Indica el nombre y rol del evaluador (Analista de Control y Cambios)? | | |
| S-03 | ¿Registra la fecha de evaluación y el checklist aplicado? | | |
| S-04 | ¿Documenta los hallazgos y las acciones correctivas aplicadas? | | |
| S-05 | ¿Indica un dictamen final (Conforme / Requiere Retrabajo)? | | |

---

## Sección E: Verificación de Reportes de Junta

| ID | Criterio | Estado | Observaciones |
|---|---|---|---|
| J-01 | ¿El reporte utiliza la plantilla oficial (`PLT-FOR_Reporte_Junta.md`)? | | |
| J-02 | ¿Incluye fecha, hora de inicio/fin y participantes? | | |
| J-03 | ¿Registra de forma clara los acuerdos, responsables y fechas límite? | | |
| J-04 | ¿Incluye el enlace a la grabación o el correo de aprobación del PO? | | |

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
**Firma:** Analista de Control y Cambios  
**Fecha:**  
