# Matriz de Responsabilidades — SGC XookTech

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Estructura organizativa del proyecto y roles del SGC.  
**Salidas:** Matriz RACI despersonalizada y asignación técnica de responsabilidades.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | STD-03 |
| Documento | Matriz de Responsabilidades del SGC |
| Marco de referencia | CMMI-DEV v2.0 PPQA / ISO/IEC 12207 |
| Versión | 3.0 |
| Fecha | 2026-05-25 |

---

## 2. Propósito
Establecer de forma clara y unificada las responsabilidades y el nivel de participación de los distintos roles del proyecto en cada una de las 8 fases del Sistema de Gestión de Calidad (SGC). Este estándar asegura la segregación de funciones, la rendición de cuentas (accountability) y la independencia de las auditorías SQA.

---

## 3. Matriz RACI del SGC
A continuación se detalla el nivel de participación de los roles despersonalizados de XookTech en los distintos procesos del ciclo de vida bajo la notación RACI:
* **R (Responsable):** Rol encargado de ejecutar de forma directa las actividades del proceso y generar los entregables.
* **A (Aprobador / Accountability):** Rol que tiene la autoridad final de decisión y firma de aceptación del entregable.
* **C (Consultado):** Rol que provee insumos, retroalimentación o asesoría técnica para la correcta ejecución del proceso.
* **I (Informado):** Rol que debe ser notificado de los avances y de la liberación de los entregables aprobados.

| Código Proceso | Fase del Ciclo de Vida | Analista de Requisitos | Analista de Gobernanza y Diseño | Líder de Desarrollo | Analista de Control y Cambios | Product Owner (PO) |
|---|---|:---:|:---:|:---:|:---:|:---:|
| **PROC-01** | Gestión de la Configuración | I | **R / A** | C | C | I |
| **PROC-02** | Requisitos de Software | **R** | I | C | C | **A** |
| **PROC-03** | Diseño de Software | I | **R / A** | C | C | I |
| **PROC-04** | Pruebas de Software | I | I | C | **R / A** | I |
| **PROC-05** | Revisiones e Inspecciones | C | C | C | **R / A** | I |
| **PROC-06** | Codificación de Software | I | I | **R / A** | C | I |
| **PROC-07** | Despliegue de Software | I | I | **R / A** | C | I |
| **PROC-08** | Mantenimiento de Software | I | **R** | C | **A** | C |

---

## 4. Directivas de Segregación de Funciones e Independencia SQA
* **Independencia en Auditorías:** Para garantizar la objetividad, el Analista de Control y Cambios (responsable de la Fase 05 y revisiones de SQA) debe actuar de forma independiente y no puede auditar ni emitir dictámenes sobre entregables en los cuales haya participado activamente como Responsable (R).
* **Firmas de Aceptación:** Ningún entregable técnico de la línea base (Requisitos o Diseño) puede considerarse liberado sin contar con la aprobación digital (A) explícita definida en la matriz.
