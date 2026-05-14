---
id: NOTE-01
titulo: Registro de Consultoria con Gemini CLI
version: "1.0"
tipo: Nota
fecha: 2026-05-08
tags:
  - consultoria
  - sgc
  - aprendizaje
---

# Registro de Consultoria - Sistema de Gestion de Calidad

Este documento registra las dudas y explicaciones clave surgidas durante la implementacion del SGC para el proyecto Visualizador de Marcos.

---

## 1. Sobre las Propiedades (Frontmatter YAML)
**Pregunta:** ¿Por qué las propiedades del `00-PROC-00_Gobernanza_Vault`?

**Respuesta:**
Las propiedades son el motor de automatizacion del Vault. Permiten:
- **Trazabilidad:** Dataview puede encontrar procesos y generar indices automaticamente.
- **Control de Versiones:** Saber si estamos usando la normativa vigente (version 1.2).
- **Rigor SQA:** Definir responsables y basar las reglas en estandares (SWEBOK, Galin).

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
