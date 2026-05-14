---
name: sqa-universidad
description: Metodología de SQA para el proyecto Visualizador de Marcos. Implementa marcos ETVX, Galin, gobernanza estricta, sincronización con GEMINI.md, registro en 08-Notes y fundamentación bibliográfica.
---

# SQA Universidad: Visualizador de Marcos

Esta skill guía al agente bajo los estándares del curso de Aseguramiento de la Calidad de Software 1.0.

## ⚠️ Mandatos Críticos
1. **Sincronización:** Al "actualizar la skill", sobrescribir `/home/axelmc/Obsidian/OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01- Proyecto/GEMINI.md`.
2. **Consultoría:** Registrar dudas técnicas en `08-Notes/Registro_Consultoria_Gemini.md` siguiendo el formato YAML y P/R.
3. **Fundamentación:** Toda recomendación técnica debe estar alineada con el [marco-teorico.md](references/marco-teorico.md) (Galin, ETVX, SWEBOK, O'Regan/Lewis).

## 1. Filosofía de Calidad (SQA)
- **Infraestructura (Galin):** Uso obligatorio de plantillas en `assets/`.
- **Rigor (ETVX):** Definir Entry, Task, Validation y Exit en cada proceso.

## 2. Pilares de la Carpeta 00-Meta
Para asegurar el cumplimiento normativo, el agente debe entender la función de cada archivo en la Authority Root:
1. **Gobernanza (00)**: Es el marco legal y contrato de operación.
2. **Plan de Acción (01)**: Es la estrategia temporal y estado de fases.
3. **Estándar de Procesos (02)**: Es el rigor metodológico (ETVX).
4. **Convenciones y Tags (03)**: Es la infraestructura de automatización (Dataview/Jerarquía).
5. **Glosario (04)**: Es el lenguaje común del proyecto.
6. **Plantillas (99)**: Son las herramientas de estandarización de Galin.

## 3. Gobernanza y Estructura
- **Nomenclatura:** Prefijos `PROC-`, `REQ-`, `CP-`, `CR-`, `INS-`, `CL-`, `NOTE-`.
- **Estructura de Carpetas:** Jerarquía obligatoria de 00 a 08.

## Recursos Integrados
- **Plantillas**: `TEMPLATE-REQ.md`, `TEMPLATE-CP.md` (en `assets/`).
- **Checklists**: `CL-02_Verificacion_Requerimientos.md`, `marco-teorico.md` (en `references/`).
