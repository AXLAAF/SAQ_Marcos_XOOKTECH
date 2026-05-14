---
id: PROC-05
titulo: Proceso 5 - Plan de Pruebas (Ciclo PDCA)
version: "1.1"
estado: En Ejecución
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-13
responsable: Axel Morales
disparador: Requerimientos y arquitectura completados
criterio_entrada: REQ profunda completada, arquitectura documentada y validada
criterio_salida: 100% Casos de prueba ejecutados, 0 defectos críticos/altos abiertos
entradas:
  - Requerimientos especificación profunda (02-Requisitos)
  - Documentación de arquitectura (03-Diseño)
  - Change Requests aprobados (07-Control)
salidas:
  - [[00-Plan_Maestro_Pruebas]]
  - Casos de prueba por módulo (CP-XX)
  - Registro de Defectos (07-Control/01-Registro_Defectos)
actividades:
  - Diseñar el plan maestro de pruebas
  - Crear casos de prueba para cada requerimiento
  - Ejecutar casos de prueba (Manual/Auto)
  - Registrar defectos encontrados
  - Analizar resultados y aplicar ciclo PDCA
roles:
  - Axel Morales (Responsable de Ejecución / Tester)
  - Samuel Blanco (Aseguramiento de Calidad / Validado)
referencias_biblio:
  - "Lewis, W. E. (2004). Software Testing and Continuous Quality Improvement."
  - "Galin, D. (2004). Software Quality Assurance: From theory to implementation."
  - "SWEBOK v4 KA5 - Software Testing"
tags:
  - proceso
  - pruebas
  - PDCA
  - SQA-Universidad
---

# Proceso 5 — Plan de Pruebas (Ciclo PDCA)

> **Fundamentación Técnica**: Siguiendo a Galin (2004), la infraestructura de SQA requiere que las pruebas no sean una fase final, sino un proceso continuo de verificación. Este proceso implementa el ciclo **PDCA (Plan-Do-Check-Act)** de Lewis para garantizar la mejora continua en la detección de defectos y la estabilidad del Visualizador de Marcos.

## 1. Estructura del Proceso (Modelo ETVX)

| Fase | Definición | Criterios / Tareas |
| :--- | :--- | :--- |
| **[E] Entry** | Criterios de Entrada | [[REQ-01]] a [[REQ-10]] verificados + Línea Base de Diseño aprobada. |
| **[T] Tasks** | Tareas Operativas | Identificación de CP, Diseño de Pasos, Ejecución y Registro de Defectos. |
| **[V] Verification** | Calidad del Plan | Revisión cruzada de la Matriz de Trazabilidad REQ -> CP por Samuel Blanco. |
| **[X] Exit** | Criterios de Salida | Reporte de Calidad firmado + Resumen de métricas de cobertura > 95%. |

## 2. Instrucciones de Trabajo (Metodología PDCA)

### Tarea 5.1: Planificación (PLAN)
1.  **Definir Alcance**: Incluir pruebas funcionales (3D, Proyección) y no funcionales (Rendimiento).
2.  **Mapeo de Trazabilidad**: Cada `REQ-XX` debe tener al menos un `CP-XX` asociado.
3.  **Priorización**: Clasificar pruebas según el riesgo de impacto en el cliente final (Enmarcame).

### Tarea 5.2: Diseño de Casos de Prueba (DO - Fase 1)
1.  **Estandarización**: Utilizar la plantilla oficial en `05-Pruebas/Modulo-XX/CP-XX.md`.
2.  **Datos de Prueba**: Definir inputs válidos (imágenes JPG/PNG) e inválidos (scripts, archivos corruptos).

### Tarea 5.3: Ejecución y Registro (DO - Fase 2)
1.  **Aislamiento**: Ejecutar pruebas en el entorno de validación antes del despliegue.
2.  **Registro de Resultados**: Comparar Resultado Esperado vs. Real. Documentar evidencias.

### Tarea 5.4: Evaluación y Acción (CHECK & ACT)
1.  **Análisis de Causa Raíz**: Si un CP falla, determinar si es defecto de código o de requerimiento.
2.  **Mejora del Proceso**: Si hay defectos recurrentes, actualizar el [[FOR-04-01_Estandar_Codificacion]].

## 3. Matriz de Seguimiento de Casos de Prueba (Sincronizada)

### Módulo 1 - Carga de Imagen (REQ-01)
| ID | Título | Referencia REQ | Estado Actual |
| :-- | :-- | :-- | :-- |
| CP-01 | Carga JPG válida | [[REQ-01]] | **Listo para Prueba** |
| CP-02 | Archivo inválido (Security) | [[REQ-01]] | **Listo para Prueba** |
| CP-03 | Imagen de alta resolución | [[REQ-01]] | **Listo para Prueba** |

### Módulo 2 - Catálogo de Marcos (REQ-04, 05, 06)
| ID | Título | Referencia REQ | Estado Actual |
| :-- | :-- | :-- | :-- |
| CP-04 | Carga inicial de catálogo | [[REQ-04]] | **Listo para Prueba** |
| CP-05 | Filtrado por modelo/estilo | [[REQ-05]] | **Listo para Prueba** |
| CP-06 | Filtrado por color/acabado | [[REQ-05]] | **Listo para Prueba** |
| CP-07 | Filtrado por dimensiones | [[REQ-05]] | **Listo para Prueba** |

### Módulo 3 - Visualización y 3D (REQ-02, 03, 07, 08, 09)
| ID | Título | Referencia REQ | Estado Actual |
| :-- | :-- | :-- | :-- |
| CP-08 | Renderizado Marco Simple | [[REQ-02]] | **En Diseño** |
| CP-09 | Configuración Marco Doble | [[REQ-07]] | **En Diseño** |
| CP-10 | Cambio de Tipo de Vidrio | [[REQ-08]] | **En Diseño** |
| CP-11 | Aplicación de María Luisa | [[REQ-09]] | **En Diseño** |
| CP-12 | Proporciones Imagen/Marco | [[REQ-02]] | **En Diseño** |

### Módulo 4 - Proyección Pantalla Secundaria (REQ-10)
| ID | Título | Referencia REQ | Estado Actual |
| :-- | :-- | :-- | :-- |
| CP-13 | Detección de Monitor Secundario | [[REQ-10]] | **Pendiente** |
| CP-14 | Sincronización en Tiempo Real | [[REQ-10]] | **Pendiente** |
| CP-15 | Fallback: Solo Pantalla Principal | [[REQ-10]] | **Pendiente** |

## 4. Métricas de Calidad de Pruebas

- **Cobertura de Requerimientos**: (REQ probados / REQ totales) * 100.
- **Densidad de Defectos**: (Total defectos / KLOC) o por Módulo.
- **Efectividad de Remoción (DRE)**: Defectos encontrados en prueba / (Encontrados en prueba + Escapados).

## 5. Referencias de Gobernanza
- [[00-PROC-00_Gobernanza_Vault]]
- [[01-Registro_Defectos]]
- [[00-Plan_Maestro_Pruebas]]

---
*Actualización conforme al Ciclo de Vida del Proyecto: 2026-05-13*
