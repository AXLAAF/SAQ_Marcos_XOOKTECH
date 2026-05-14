---
id: PROC-07
titulo: Proceso 7 - Control de Calidad y Cambios
version: "1.2"
estado: Activo
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-13
responsable: Axel Morales
disparador: Ejecución de procesos y detección de desviaciones
criterio_entrada: Artefactos de software generados o cambios solicitados
criterio_salida: Línea base verificada y métricas reportadas
entradas:
  - [[02-REG-03_Registro_Defectos]]
  - [[05-INS-01_Inspeccion_Requerimientos]]
salidas:
  - [[01-STD-08_Dashboard_Calidad]]
  - [[03-PROC-08_Control_Cambios]]
actividades:
  - Monitorear métricas de calidad (Dashboard)
  - Gestionar el ciclo de vida de los defectos
  - Realizar inspecciones Fagan en hitos críticos
  - Procesar solicitudes de cambio (Change Requests)
roles:
  - Samuel Blanco (Aseguramiento de Calidad / Autoridad)
  - Axel Morales (Control Operativo / Registro)
referencias_biblio:
  - "Galin, D. (2004). Software Quality Assurance: From theory to implementation."
  - "O'Regan, G. (2010). A Practical Approach to Software Quality."
tags:
  - meta/proceso
  - fase/control
  - tipo/proceso
  - estado/activo
---

# Proceso 7 — Control de Calidad y Cambios

> **Fundamentación**: Según Galin (2004), el control de calidad es el conjunto de actividades destinadas a evaluar la calidad de los productos de software. Este proceso integra el control de cambios y las inspecciones técnicas para asegurar que la evolución del sistema no comprometa su integridad.

## 1. Estructura del Proceso (Modelo ETVX)

| Fase | Definición | Detalles |
| :--- | :--- | :--- |
| **[E] Entry** | Criterios de Entrada | Defecto detectado o solicitud de cambio en [[07-CR-00_Reporte_Retroactivo]]. |
| **[T] Tasks** | Tareas Operativas | Registro, clasificación de severidad y asignación de responsables. |
| **[V] Verification** | Calidad del Control | Auditoría de cierres de tickets por Samuel Blanco. |
| **[X] Exit** | Criterios de Salida | Métricas actualizadas en [[01-STD-08_Dashboard_Calidad]]. |

## 2. Jerarquía de Control

1.  **Dashboard (Prioridad 01)**: Visibilidad macro del estado de calidad.
2.  **Defectos (Prioridad 02)**: Gestión reactiva de fallos técnicos.
3.  **Cambios (Prioridad 03-11)**: Gestión proactiva de la evolución del alcance.

---
*Actualización conforme al Estándar de Prioridad SQA: 2026-05-13*
