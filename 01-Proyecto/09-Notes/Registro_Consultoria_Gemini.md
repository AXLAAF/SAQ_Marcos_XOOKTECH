# Registro de Consultoria - Sistema de Gestion de Calidad
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Entrada de Gobernanza SGC
**Salidas:** Salida de Gobernanza SGC

Este documento registra las dudas y explicaciones clave surgidas durante la implementacion del SGC para el proyecto Visualizador de Marcos.

---

## 1. Sobre las Propiedades (Frontmatter YAML)
**Pregunta:** ¿Por qué las propiedades del `00-PROC-00_Gobernanza_Vault`?

**Respuesta:**
Las propiedades son el motor de automatizacion del Vault. Permiten:
- **Trazabilidad:** Dataview puede encontrar procesos y generar indices automaticamente.
- **Control de Versiones:** Saber si estamos usando la normativa vigente (version 1.2).

---

## 2. Sobre la Fundamentacion
**Pregunta:** ¿En qué se basa la fundamentacion de la gobernanza?

**Respuesta:**
Se basa en dos pilares cientificos:
1. **Infraestructura de Daniel Galin (2004):** Establece que la calidad requiere plantillas y procedimientos previos para evitar errores humanos.
2. **Modelo ETVX (IBM):** Define criterios estrictos de entrada (**E**ntry), tareas (**T**asks), verificacion (**V**erification) y salida (**X**it) para que los procesos sean profundos y no generales.

---

## 3. Estructura y Orden
**Duda:** Necesidad de que los archivos esten escorados por importancia.

**Solucion:**
Se implemento una numeracion de dos digitos en `00-Meta`:
- `00-` Autoridad Maxima (Gobernanza).
- `01-` Estrategia (Plan de Accion).
- ...
- `99-` Archivos auxiliares (Plantillas).

---
*Este registro se actualizara conforme avancen las preguntas del equipo.*

---

## 4. Pilares del SGC (Revision Final 00-Meta)
**Pregunta:** ¿Como se define la funcion de cada archivo en la Authority Root (00-Meta)?

**Respuesta:**
Tras la auditoria profunda, se establece la siguiente jerarquia funcional:
1. **Gobernanza (00)**: Marco legal y reglas de operacion.
2. **Plan de Accion (01)**: Hoja de ruta y gestion de fases.
3. **Estandar de Procesos (02)**: Definicion del rigor metodológico (ETVX).
4. **Convenciones y Tags (03)**: Motor de automatizacion y organizacion visual.
5. **Glosario (04)**: Diccionario tecnico para evitar ambiguedades.
6. **Plantillas (99)**: Activos de infraestructura de Daniel Galin.

*Esta sintesis fue integrada en los mandatos del agente (GEMINI.md) para garantizar cumplimiento.*

---

## 5. Reingeniería del Proceso de Requisitos (PROC-02)
**Sesion:** 2026-05-13
**Consultante:** Analista Técnico
**Tema:** Control de Scope Creep y Evidencia de Aprobación.

**Pregunta:** ¿Cómo podemos integrar las mejores prácticas de CMMI-REQM y ETVX en nuestro flujo de Obsidian+Relay para evitar el scope creep y la falta de evidencia en las aprobaciones?

**Respuesta:** Se rediseñó el `PROC-02` introduciendo una segregación de carpetas (`00-Pendientes` -> `01-Aprobados`) que actúa como control de configuración (CMMI-CM). Se actualizó la `TEMPLATE-REQ` para incluir criterios BDD medibles y un campo obligatorio para evidencia de validación (capturas/correos). Además, se implementó una Matriz de Trazabilidad en Markdown para asegurar el vínculo bidireccional entre requisitos y pruebas, cumpliendo con los estándares de Galin y SWEBOK v4.

---

## 6. Despersonalización y Definición de Roles Funcionales
**Sesion:** 2026-05-14
**Consultante:** Analista Técnico
**Tema:** Transición de nombres propios a Roles Funcionales y sus responsabilidades.

**Pregunta:** ¿Cómo se definen las responsabilidades de cada rol tras la despersonalización y qué funciones específicas tiene el Líder SQA?

**Respuesta:**
Tras la eliminación de nombres propios, el proyecto se organiza bajo tres pilares de responsabilidad técnica y operativa definidos en el [[01-PLAN-01_Accion_SQA]]:

1. **Líder SQA (Implementación y Operaciones):**
   - **Responsabilidad:** Es el pilar técnico del proyecto. Se encarga de la **Fase 4 (Codificación)**, asegurando la integridad de los módulos Python y el repositorio en GitHub.
   - **Operaciones:** Lidera la **Fase 6 (Mantenimiento)** y la **Fase 8 (Despliegue)**, documentando las guías de instalación y soporte técnico.
   - **Gobernanza:** Sistematiza los procesos operativos para que el sistema sea entregable y mantenible.

2. **Analista Técnico (Estrategia y Verificación):**
   - **Responsabilidad:** Lidera la **Fase 1 (Línea Base)**, la **Fase 3 (Diseño)** y la **Fase 5 (Pruebas)**.
   - **Calidad:** Actúa como auditor de procesos, asegurando que la trazabilidad ETVX se cumpla en cada fase.

3. **Analista SQA (Análisis y Control de Calidad):**
   - **Responsabilidad:** Se encarga de la **Fase 2 (Requisitos)** y la **Fase 7 (Control)**.
   - **Trazabilidad:** Su función crítica es cerrar la **Matriz de Trazabilidad (RTM)**, vinculando los requerimientos con los reportes de control e inspecciones.

*Esta estructura garantiza que el SGC funcione por procesos y no dependa de la presencia de individuos específicos.*