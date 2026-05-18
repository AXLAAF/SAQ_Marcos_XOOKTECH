---
id: META-04
titulo: Estandar de Estructura de Procesos
version: "1.0"
estado: Activo
tipo: Estandar
fecha_creacion: 2026-05-08
ultima_revision: 2026-05-08
responsable: Axel Morales
referencias_biblio:
  - "SWEBOK v4 KA8 - Software Engineering Process"
  - "O'Regan Cap. 5 - SPICE Level 3"
tags:
  - meta/estandar
  - procesos
---

# Estandar de Estructura de Procesos

> Este documento define la estructura obligatoria para todos los procesos documentados en el SGC del Visualizador de Marcos. El objetivo es garantizar la "profundidad" y "conexion" requerida para el aseguramiento de la calidad (SQA).

---

## 1. Justificacion y Rigor

Segun SWEBOK v4, un proceso bien definido debe ser repetible y medible. Para este proyecto, no basta con listar actividades; cada proceso debe actuar como una funcion de calidad: **Salida = Proceso(Entradas)**.

## 2. Secciones Obligatorias

Todo archivo de proceso (`PROC-XX`) debe contener las siguientes secciones:

### 2.1 Frontmatter YAML
Debe incluir:
- `disparador`: Que evento inicia el proceso.
- `criterio_entrada`: Condicion sine-qua-non para empezar.
- `criterio_salida`: Que debe cumplirse para darlo por cerrado.
- `entradas` y `salidas`: Listas de [[Wikilinks]] a documentos reales.

### 2.2 Definicion Operativa
Una tabla resumen que facilite la lectura rapida de las responsabilidades y objetivos del proceso.

### 2.3 Actividades Detalladas
No solo una lista, sino una descripcion de **como** se realiza la actividad. Si la actividad genera un documento, debe mencionarlo explicitamente.

### 2.4 Matriz de Entradas y Salidas
Una tabla que relacione cada entrada con su actividad correspondiente y el entregable resultante.

| Entrada (Input) | Actividad (Activity) | Salida (Output) |
| :--- | :--- | :--- |
| [[Documento_A]] | Revision de X | [[Documento_B]] |

### 2.5 Metricas de Proceso
Todo proceso debe definir al menos una metrica cuantitativa para evaluar su efectividad (ej. Numero de defectos encontrados en inspeccion / Total de requerimientos).

---

## 3. Reglas de Conexion (Trazabilidad)

1.  **Entradas**: Deben ser documentos existentes en el vault o datos externos documentados.
2.  **Salidas**: Deben convertirse en entradas de procesos subsiguientes (ver Arquitectura en [[PROC-00_Gobernanza_Vault]]).
3.  **Enlaces**: Se debe usar la sintaxis `[[Fase/Archivo]]` para evitar ambiguedades en el vault.

---

*Documento creado: 2026-05-08 | Por Axel Morales (SQA Support)*
