
# Dashboard de Calidad - Visualizador de Marcos
**Responsable:** Analista de Control y Cambios
**Entradas:** Registros de Defectos e Incidentes
**Salidas:** Solicitudes de Cambio Aprobadas e Informes de Inspección

---

> Este documento proporciona una vista consolidada del estado de calidad del proyecto, integrando metricas de requerimientos, pruebas, cambios y defectos.

---

## 1. Resumen Ejecutivo

| Indicador | Valor | Estado |
| :-- | :-- | :-- |
| Total Requerimientos | 10 | - |
| Requerimientos Completados | 6 | En Progreso |
| Requerimientos Pendientes | 4 | Pending |
| Total Change Requests | 4 | En Analisis |
| Total Casos de Prueba | 15 | Pendiente |
| Defectos Abiertos | 0 | N/A |

---

## 2. Metric as de Requerimientos

### 2.1 Estado de Requerimientos

```dataview
TABLE id, titulo, estado, prioridad
FROM "02-Requerimientos"
SORT id ASC
```

### 2.2 Requerimientos sin Trazabilidad

```dataview
TABLE id, titulo, estado
FROM "02-Requerimientos"
WHERE length(casos_prueba) = 0
```

### 2.3 Distribución por Prioridad

```dataview
TABLE prioridad, count() AS total
FROM "02-Requerimientos"
GROUP BY prioridad
```

---

## 3. Metric as de Change Requests

### 3.1 Estado de CRs

```dataview
TABLE id, titulo, estado, impacto_tiempo_dias, impacto_costo_mxn
FROM "03-Control_Cambios"
SORT id ASC
```

### 3.2 CRs Pendientes de Aprobacion

```dataview
TABLE id, titulo, tipo_cambio, solicitado_por, fecha_solicitud
FROM "03-Control_Cambios"
WHERE estado = "Pendiente"
SORT fecha_solicitud DESC
```

---

## 4. Metric as de Pruebas

### 4.1 Estado de Casos de Prueba

```dataview
TABLE id, titulo, modulo, estado
FROM "04-Pruebas"
WHERE contains(modulo, "Modulo")
SORT id ASC
```

### 4.2 Resumen por Estado

```dataview
TABLE estado, count() AS total
FROM "04-Pruebas"
GROUP BY estado
```

### 4.3 Resumen por Modulo

```dataview
TABLE modulo, count() AS total_casos, sum(where(estado="Fallido",1,0)) AS fallidos
FROM "04-Pruebas"
GROUP BY modulo
```

---

## 5. Metric as de Defectos

### 5.1 Registro de Defectos

```dataview
TABLE id, severidad, estado, fecha_deteccion, responsable
FROM "07-Metricas"
WHERE tipo = "defecto"
SORT fecha_deteccion DESC
```

### 5.2 Defectos por Severidad

```dataview
TABLE severidad, count() AS total
FROM "07-Metricas"
WHERE tipo = "defecto"
GROUP BY severidad
```

---

## 6. Metric as de Procesos

### 6.1 Estado de Procesos

| Proceso | Estado | Responsable | Ultima Actualizacion |
| :-- | :-- | :-- | :-- |
| PROC-01: Recuperacion Linea Base | En_Progreso | Líder SQA | 2026-03-19 |
| PROC-02: Especificacion Requerimientos | Pendiente | Analista Técnico | - |
| PROC-03: Control de Cambios | Pendiente | Líder SQA | - |
| PROC-04: Arquitectura Sistema | Pendiente | Analista Técnico | - |
| PROC-05: Plan de Pruebas | Pendiente | Analista Técnico | - |
| PROC-06: Inspecciones | Pendiente | Líder SQA | - |

---

## 7. Indicadores Clave de Proceso (KPI)

### 7.1 Completitud de Requerimientos

| Metrica | Formula | Meta | Actual |
| :-- | :-- | :-- | :-- |
| % REQ con Criterios de Aceptacion | REQ con CA / Total REQ | 100% | 0% |
| % REQ con Trazabilidad | REQ con CP / Total REQ | 100% | 0% |
| % REQ con Reglas de Negocio | REQ con RN / Total REQ | 100% | 0% |

### 7.2 Eficacia de Pruebas

| Metrica | Formula | Meta | Actual |
| :-- | :-- | :-- | :-- |
| % CP Ejecutados | CP ejecutados / Total CP | 100% | 0% |
| % CP Exitosos | CP exitosos / CP ejecutados | 95% | N/A |
| Densidad de Defectos | Defectos / Total CP | < 0.1 | N/A |

### 7.3 Control de Cambios

| Metrica | Formula | Meta | Actual |
| :-- | :-- | :-- | :-- |
| CR processed | CR approved / Total CR | 100% | 0% |
| Avg tiempo CR | Dias promedio de aprobacion | < 5 | N/A |

---

## 8. Acciones Recomendadas

Basado en el analisis de metricas, se recomiendan las siguientes acciones:

1. [ ] Completar PROC-01 para establecer linea base
2. [ ] Especificar requerimientos faltantes (PROC-02)
3. [ ] Aprobar Change Requests pendientes
4. [ ] Ejecutar casos de prueba

---

## 9. Referencias

- [[01-Gestion de la configuracion/01-PROC-01_Gobernanza_Vault|PROC-01 Gobernanza Vault]]
- [[09-Notes/01-Linea_Base-Original/00-PROC-01_Recuperacion_Linea_Base|PROC-01 Recuperación de Línea Base]]
- [[02-Requisitos/02-PROC-02_Especificacion_Requerimientos|PROC-02 Especificación de Requerimientos]]
- [[05-Revisiones e inspecciones/05-PROC-05.1_Control_Cambios|PROC-08 Control de Cambios]]
- [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan de Pruebas]]
- [[05-Revisiones e inspecciones/02-Calidad_Control/02-REG-03_Registro_Defectos|REG-03 Registro de Defectos]]

---

*Dashboard actualizado: 2026-03-19 | Proxima actualizacion: 2026-03-26*