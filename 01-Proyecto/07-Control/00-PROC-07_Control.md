---
id: PROC-07
titulo: Proceso de Control de Calidad y Configuracion
version: "1.0"
responsable: Carlos Yonson
disparador: Cualquier cambio en artefactos o hito de fase.
criterio_entrada: Artefacto listo para revision o solicitud de cambio (CR).
criterio_salida: Reporte de calidad aprobado y linea base etiquetada.
entradas:
  - "[[02-Requisitos/REQ-XX]]"
  - "[[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]"
salidas:
  - "[[07-Control/CTRL-01_Matriz_Trazabilidad]]"
  - "[[07-Control/INS-XX_Reportes_Inspeccion]]"
  - "[[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/00-Dashboard_Calidad]]"
---

# PROC-07: Proceso de Control

> **Objetivo**: Garantizar la integridad de los artefactos y medir el desempeño del SGC.

## 1. Actividades (Task)

| Entrada | Actividad | Salida |
| :--- | :--- | :--- |
| Solicitud | Gestion de Control de Cambios (SCC) | [[CR-XX]] |
| Artefactos | Inspecciones Formales (Fagan/Galin) | [[INS-XX]] |
| Datos Pruebas | Generacion de Metricas de Defectos | [[CTRL-Dashboard]] |

## 2. Validacion (Verification)

1.  **Checklist de Calidad**: Todo documento debe pasar su `CL-XX` antes de ser "Base".
2.  **Revision de SCM**: Verificar que la version en el vault coincida con la del repositorio.

---
*Documento sistematizado segun ETVX.*
