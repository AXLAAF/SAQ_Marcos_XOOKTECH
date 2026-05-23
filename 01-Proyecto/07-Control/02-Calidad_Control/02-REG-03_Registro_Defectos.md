
# Registro de Defectos - Visualizador de Marcos
**Responsable:** Analista de Control y Cambios
**Entradas:** Registros de Defectos e Incidentes
**Salidas:** Solicitudes de Cambio Aprobadas e Informes de Inspección

---

> Este documento es el repositorio central de todos los defectos encontrados durante el proceso de pruebas. Cada defecto debe ser registrado, rastreado y cerrado siguiendo el ciclo de vida definido.

---

## 1. Ciclo de Vida del Defecto

```
Nuevo -> Asignado -> En_Progreso -> Resuelto -> Cerrado
                \-> No_Es_Defecto -> Cerrado
                \-> Diferido -> Cerrado
```

### Estados del Defecto

| Estado | Descripcion |
| :-- | :-- |
| Nuevo | Defecto detectado, pendiente de revision |
| Asignado | Defecto asignado a un responsable |
| En_Progreso | Correccion en desarrollo |
| Resuelto | Correccion implementada, pendiente de verificacion |
| Cerrado | Correccion verificada y aceptada |
| No_Es_Defecto | Confirmado que no es un defecto |
| Diferido | Defecto postergado para version futura |

### Severidad del Defecto

| Severidad | Descripcion | Ejemplo |
| :-- | :-- | :-- |
| Critico | Sistema no funcional, perda de datos | App no inicia |
| Alto | Funcion principal no funciona | No se carga imagen |
| Medio | Funcion secundaria afectada | Filtro no funciona |
| Bajo | Defecto cosmético, inconvenience menor | Error tipografico |

### Prioridad del Defecto

| Prioridad | Descripcion |
| :-- | :-- |
| Alta | Debe corregirse antes del release |
| Media | Debe corregirse si hay tiempo |
| Baja | Correccion deseable pero no critica |

---

## 2. Plantilla de Registro de Defecto

```yaml
---
id: DEF-XX
titulo: ""
estado: Nuevo
severidad: Alta
prioridad: Alta
modulo: ""
caso_prueba: ""
fecha_deteccion: YYYY-MM-DD
detectado_por: ""
asignado_a: ""
fecha_asignacion: ""
fecha_resolucion: ""
fecha_cierre: ""
tags:
  - defecto
  - modulo/[nombre]
---
```

### Seccion Detallada del Defecto

```markdown
# DEF-[ID]: [Titulo del Defecto]

## 1. Informacion General
| Campo | Valor |
| :-- | :-- |
| ID | DEF-XX |
| Estado | [Estado] |
| Severidad | [Critico/Alto/Medio/Bajo] |
| Prioridad | [Alta/Media/Baja] |
| Modulo | [Nombre] |
| Caso de Prueba | `CP-XX` |

## 2. Descripcion
[Descripcion detallada del defecto]

## 3. Pasos para Reproducir
1. [Paso 1]
2. [Paso 2]
3. [Paso 3]

## 4. Resultado Esperado
[Que deberia ocurrir]

## 5. Resultado Actual
[Que esta ocurriendo]

## 6. Entorno
- Sistema Operativo: [OS]
- Navegador: [Version]
- Version de la App: [X.X]

## 7. Evidencia
[Capturas de pantalla, logs, etc.]

## 8. Historial
| Fecha | Accion | Responsable |
| :-- | :-- | :-- |
| YYYY-MM-DD | Detectado | [Nombre] |
| YYYY-MM-DD | Asignado | [Nombre] |
| YYYY-MM-DD | Resuelto | [Nombre] |
| YYYY-MM-DD | Cerrado | [Nombre] |

## 9. Resolucion
[Como se resolvio el defecto]

## 10. Verificacion
[Como se verifico que la correccion funciona]
```

---

## 3. Registro de Defectos

### 3.1 Defectos Activos

| ID | Titulo | Severidad | Prioridad | Modulo | Estado | Asignado a |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| - | - | - | - | - | - | - |

*No hay defectos registrados actualmente*

### 3.2 Historial de Defectos Cerrados

| ID | Titulo | Severidad | Modulo | Fecha Cierre |
| :-- | :-- | :-- | :-- | :-- |
| - | - | - | - | - |

*No hay defectos cerrados*

---

## 4. Metric as de Defectos

### 4.1 Resumen por Severidad

| Severidad | Total | Abiertos | Cerrados |
| :-- | :-- | :-- | :-- |
| Critico | 0 | 0 | 0 |
| Alto | 0 | 0 | 0 |
| Medio | 0 | 0 | 0 |
| Bajo | 0 | 0 | 0 |

### 4.2 Resumen por Modulo

| Modulo | Total | Abiertos | Cerrados |
| :-- | :-- | :-- | :-- |
| Carga | 0 | 0 | 0 |
| Catalogo | 0 | 0 | 0 |
| Previsualizacion | 0 | 0 | 0 |
| Pantalla Secundaria | 0 | 0 | 0 |

### 4.3 Tendencia de Defectos

```dataview
TABLE date_format(date(date_deteccion), "yyyy-MM") AS mes, count() AS total
FROM "07-Metricas"
WHERE tipo = "defecto"
GROUP BY date(date_deteccion)
SORT date(date_deteccion) DESC
```

---

## 5. Criterios de Cierre de Defecto

Para cerrar un defecto, deben cumplirse:

- [ ] Correccion implementada
- [ ] Verificacion exitosa en ambiente de pruebas
- [ ] Casos de prueba re-ejecutados exitosamente
- [ ] Documentacion actualizada si es necesario
- [ ] Aprobacion del responsable de calidad

---

## 6. Referencias

- [[00-Meta/00-PROC-00_Gobernanza_Vault|PROC-00 Gobernanza Vault]]
- [[05-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan de Pruebas]]
- [[07-Control/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08 Dashboard de Calidad]]

---

*Registro creado: 2026-03-19 | Ultima actualizacion: 2026-03-19*