---
id: PROC-01
titulo: Proceso 1 - Recuperacion de Linea Base
version: "1.4"
estado: Completado
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-08
responsable: Líder SQA
disparador: Acuerdo del equipo de iniciar la documentacion formal
criterio_entrada: Acceso a mensajes de WhatsApp, correos, codigo fuente en GitHub, y contrato formal
criterio_salida: Propuesta revisada y contrato formal verificado contra alcance documentado
entradas:
  - Mensajes de WhatsApp
  - [[01-Baseline/06-Contrato_Desarrollo]]
salidas:
  - [[01-Baseline/01-Acta_Inicio]]
  - [[01-Baseline/02-Propuesta_Recuperada]]
  - [[01-Baseline/03-Acuerdos_Cliente]]
  - [[01-Baseline/04-Guia_Entrevista_PO]]
  - [[01-Baseline/05-Minuta_Entrevista]]
actividades:
  - Reconstruccion de linea base mediante elicitacion profunda (Líder SQA/Analista Técnico).
  - Digitalizacion de acuerdos contractuales y verbales.
  - Verificacion de consistencia entre propuesta y contrato.
roles:
  - Líder SQA (Lider/PO)
  - Analista Técnico (SQA/Dev)
referencias_biblio:
  - SWEBOK v4 KA1 6.2
  - O'Regan Cap. 1.5.1
  - Daniel Galin (Infraestructura SQA)
tags:
  - proceso/etvx
  - baseline
---

# Proceso 1 — Recuperacion de la Linea Base

> **Justificacion**: Segun Daniel Galin, la calidad requiere una infraestructura estable. Este proceso recupera la linea base (Baseline) de un proyecto que carecia de documentacion formal.

## 1. Estructura ETVX

| Fase | Definicion | Detalles |
| :--- | :--- | :--- |
| **[E] Entry** | Entrada | Contrato firmado + Acceso a evidencias (WA/Email). |
| **[T] Tasks** | Tareas | Elicitacion, Redaccion de Propuesta y Digitalizacion de Contrato. |
| **[V] Verification** | Calidad | Cruce de clausulas contractuales vs Propuesta tecnica. |
| **[X] Exit** | Salida | Linea base aprobada (Documentos 00 a 05). |

## 2. Instrucciones de Trabajo
1.  **Elicitacion**: Ejecutar la guia estructurada [[01-Baseline/04-Guia_Entrevista_PO]].
2.  **Documentacion**: Redactar la propuesta recuperada [[01-Baseline/02-Propuesta_Recuperada]].
3.  **Formalizacion**: Validar acuerdos verbales en [[01-Baseline/03-Acuerdos_Cliente]].
4.  **Cierre**: Verificar que todos los REQ del contrato [[01-Baseline/06-Contrato_Desarrollo]] estan mapeados.

## 3. Matriz de Entradas y Salidas
| Entrada (Input) | Actividad (Activity) | Salida (Output) |
| :--- | :--- | :--- |
| Mensajes WA/Email | Recuperacion de acuerdos | [[01-Baseline/03-Acuerdos_Cliente]] |
| Contrato Fisico | Digitalizacion | [[01-Baseline/06-Contrato_Desarrollo]] |
| Respuestas Elicitacion | Sintesis Tecnica | [[01-Baseline/02-Propuesta_Recuperada]] |

---
*Ultima actualizacion: 2026-05-08 | Estado: COMPLETADO*
