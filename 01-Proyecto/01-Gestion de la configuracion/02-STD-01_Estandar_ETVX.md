# Estándar ETVX — Ciclo de Vida de Procesos

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Directrices del SGC y ciclo de mejora continua PDCA.  
**Salidas:** Definición técnica de procesos unificada bajo el estándar de XookTech.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | STD-01 |
| Documento | Estándar Metodológico ETVX de Procesos |
| Marco de referencia | CMMI-DEV v2.0 / ISO/IEC 12207 |
| Versión | 3.0 |
| Fecha | 2026-05-25 |

---

## 2. Propósito
Establecer una notación técnica homogénea para describir y ejecutar los procesos de ingeniería de software y control de calidad en XookTech. El estándar ETVX garantiza que cada fase cuente con criterios de entrada controlados, tareas operacionales explícitas, filtros independientes de verificación y criterios de salida verificables.

---

## 3. Modelo ETVX (Estructura de Fases)

Todo proceso o fase integrada al Sistema de Gestión de Calidad (SGC) de XookTech debe definirse y controlarse bajo el modelo de cuatro cuadrantes ETVX:

### 3.1 Criterios de Entrada (Entry Criteria - E)
Define el estado inicial y los insumos indispensables requeridos para poder iniciar las tareas del proceso:
* **Insumos Requeridos:** Documentos, especificaciones o artefactos físicos firmados que sirven como materia prima.
* **Estado de la Configuración:** Los insumos deben estar debidamente identificados, registrados y ubicados en el directorio oficial en Obsidian.
* **Validación de Entrada:** Verificación obligatoria de la suficiencia y claridad técnica de los insumos antes de comenzar.

### 3.2 Tareas Operacionales (Tasks - T)
Describe las actividades específicas, secuenciales y repetibles que el responsable del proceso debe ejecutar para transformar los insumos en salidas:
* **Secuencia de Pasos:** Flujo procedimental paso a paso detallado y exento de ambigüedades.
* **Roles Asignados:** Cada tarea debe tener asignado explícitamente el rol institucional despersonalizado encargado de su ejecución.
* **Uso de Formatos:** Aplicación obligatoria de las plantillas oficiales del proceso en Obsidian.

### 3.3 Criterios de Verificación (Verification - V)
Filtro de control de calidad independiente ejecutado antes de autorizar la salida del proceso:
* **Checklists de Calidad:** Aplicación obligatoria de los checklists oficiales unificados de la fase.
* **Porcentaje de Conformidad:** Medición cuantitativa del cumplimiento de los criterios mínimos establecidos.
* **Ciclo de Reproceso:** Si se detectan desviaciones o incumplimientos, se rechaza la liberación del paquete y se otorga un plazo máximo de 24 horas para corregir y volver a someter a verificación.

### 3.4 Criterios de Salida (Exit Criteria - X)
Establece las condiciones y entregables verificados que deben cumplirse para dar por finalizada la fase de forma exitosa:
* **Artefactos Verificados:** Entregables técnicos completos, sin marcadores pendientes (TBD) y auditados de forma conforme.
* **Firma Digital de Aprobación:** Dictámenes de SQA o firmas de aceptación del Product Owner inyectadas en los documentos.
* **Actualización del SGC:** Registro y segregación del artefacto en la carpeta de aprobados y actualización de la Matriz RTM general.

---

## 4. Gobernanza y Adherencia
* **Obligatoriedad:** Ningún desarrollador o analista técnico puede omitir el flujo ETVX de una fase.
* **Auditoría Independiente:** El Analista de Control y Cambios verifica de forma periódica que los archivos y bitácoras operacionales demuestren la disciplina y el cumplimiento operacional del modelo ETVX.
