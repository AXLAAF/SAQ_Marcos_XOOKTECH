---
id: PROC-02
titulo: Proceso 2 - Especificacion de Requerimientos
version: "3.0"
estado: Activo
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-14
responsable: Líder SQA (Lider) / Analista Técnico (Desarrollador)
autor: Analista SQA / Analista Técnico
disparador: Solicitud de cambio o nueva funcionalidad por parte del cliente
criterio_entrada: Solicitud documentada en acta, correo o minuta de entrevista
criterio_salida: Nota de requerimiento en estado "Aprobado" en carpeta 01-Aprobados
entradas:
  - [[00-Meta/05-PROC-01_Gestion_Documental]]
  - [[00-Meta/01-PLAN-01_Accion_SQA]]
salidas:
  - REQ-XXX.md (especificacion detallada en 01-Aprobados)
  - [[02-Requisitos/01-STD-03_Matriz_Trazabilidad]]
referencias_biblio:
  - "SWEBOK v4 KA1 - Software Requirements"
  - "Galin, D. (2004). Software Quality Assurance"
tags:
  - meta/proceso
  - fase/requisitos
  - tipo/proceso
  - estado/activo
---

# Proceso 2 — Especificación de Requerimientos

> **Fundamentación**: Este proceso sigue los lineamientos de CMMI-DEV (REQM) e ISO 9001, utilizando el modelo **ETVX** y la infraestructura de **Galin** para asegurar que cada requerimiento sea medible, rastreable y aprobado formalmente.

## 1. Estructura del Proceso (Modelo ETVX)

| Fase | Definición | Detalles |
| :--- | :--- | :--- |
| **[E] Entry** | Criterios de Entrada | Solicitud capturada en minuta o canal oficial. |
| **[T] Tasks** | Tareas Operativas | Fases 1 a 4: Captura, Revisión, Validación y Línea Base. |
| **[V] Verification** | Verificación de Calidad | Aplicación de Checklist de Calidad + Revision Líder SQA/Analista Técnico. |
| **[X] Exit** | Criterios de Salida | Archivo en `01-Aprobados` con estado "Aprobado". |

## 2. Proceso Detallado (Refinamiento SQA)

### Paso 1: Captura de Requisitos (Planear)
**NT-1:** Se centraliza toda solicitud en una nota inicial en `00-Pendientes` con ID único `REQ-XXX` para evitar el "scope creep".
- Líder SQA crea el archivo `REQ-XXX` en `02-Requisitos/00-Pendientes/`.

### Paso 2: Revisión y Especificación (Hacer)
**NT-2:** Uso obligatorio de plantilla con criterios BDD (Dado/Cuando/Entonces).
- Analista Técnico aplica la plantilla y define criterios de aceptacion medibles.
- Se estima el esfuerzo y se asigna prioridad.

### Paso 3: Validación con el Cliente (Verificar)
**NT-3:** Toda aprobación debe ser por escrito (correo o captura de WhatsApp) para evitar conflictos de costos.
- Líder SQA presenta el REQ al cliente y obtiene aprobacion formal.
- Se vincula la evidencia en el documento.

### Paso 4: Línea Base y Trazabilidad (Actuar)
**NT-4:** La segregación de carpetas (`00-Pendientes` -> `01-Aprobados`) actúa como control de configuración (CMMI-CM).
- El archivo aprobado se mueve a `02-Requisitos/01-Aprobados/`.
- Se actualiza la [[02-Requisitos/01-STD-03_Matriz_Trazabilidad]].

## 3. Justificación de Mejoras (Por Analista SQA)
- **Centralización**: Mitiga el crecimiento descontrolado del alcance.
- **Plantilla BDD**: Elimina la ambigüedad en las pruebas.
- **Evidencia**: Proporciona respaldo legal y técnico.
- **Segregación**: Asegura que el equipo solo trabaje sobre lo validado.

## 4. Métricas de Éxito
- **Tiempo de Ciclo**: ≤ 5 días hábiles.
- **Calidad**: 100% de REQ con criterios medibles.
- **Formalidad**: 100% con evidencia adjunta.

---
*Refinamiento: Analista SQA (2026-05-13) | Integracion de Gobernanza: Analista Técnico (2026-05-14)*
