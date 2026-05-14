---
id: PROC-05
titulo: Proceso 5 - Plan de Pruebas (PDCA)
version: "1.0"
estado: Pendiente
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-03-19
responsable: Axel Morales
disparador: Requerimientos y arquitectura completados
criterio_entrada: REQ profunda completada, arquitectura documentada
criterio_salida: Casos de prueba ejecutados y reportados
entradas:
  - Requerimientos especificacion profunda
  - Documentacion de arquitectura
  - Change Requests aprobados
salidas:
  - 00-Plan_Maestro_Pruebas.md
  - Casos de prueba por modulo
  - Reportes de ejecucion
actividades:
  - Disenar el plan maestro de pruebas
  - Crear casos de prueba para cada requerimiento
  - Ejecutar casos de prueba
  - Registrar defectos encontrados
  - Analizar resultados
  - Aplicar ciclo PDCA
roles:
  - Axel Morales (ejecutor)
  - Samuel Blanco (validacion)
referencias_biblio:
  - "Lewis Cap. 3-4 - Ciclo PDCA y plan de pruebas"
  - "SWEBOK v4 KA5 - Pruebas de Software"
tags:
  - proceso
  - pruebas
  - PDCA
---

# Proceso 5 — Plan de Pruebas (Ciclo PDCA)

> **Fundamentacion**: Segun Lewis (2004), un proceso de pruebas sistematico debe seguir el ciclo PDCA para garantizar que los defectos no solo se detecten, sino que se prevengan en el futuro. Este proceso utiliza el modelo **ETVX** para operativizar las pruebas de software basandose en la especificacion profunda de requerimientos.

## 1. Estructura del Proceso (ETVX)

| Fase | Definicion | Detalles |
| :--- | :--- | :--- |
| **[E] Entry** | Criterios de Entrada | [[REQ-01]] a [[REQ-10]] en estado "Verificado" + [[05-Contrato_Desarrollo]]. |
| **[T] Tasks** | Tareas Operativas | Pasos 5.1 a 5.4 basados en Ciclo PDCA (Ver Seccion 2). |
| **[V] Verification** | Calidad del Plan | Walkthrough del Plan Maestro + Validacion de Trazabilidad REQ->CP. |
| **[X] Exit** | Criterios de Salida | 100% de CP ejecutados + Reporte de Calidad aprobado por Samuel. |

## 2. Instrucciones de Trabajo (Paso a Paso)

### Tarea 5.1: Planificacion (PLAN)
1.  **Definir Alcance**: Identifique qué módulos serán probados (Carga, Catálogo, 3D, Pantalla Secundaria).
2.  **Identificar Casos de Prueba (CP)**: Por cada Criterio de Aceptación (CA) definido en los [[REQ-XX]], identifique al menos un escenario de prueba.
3.  **Priorizar**: Marque como "Alta" las pruebas que validen clausulas del [[05-Contrato_Desarrollo]].

### Tarea 5.2: Diseño de Pruebas (DO - Parte 1)
1.  **Crear Artefactos**: Para cada prueba identificada, cree un archivo en `05-Pruebas/[Modulo]/` con el nombre `CP-[ID]_[Nombre].md`.
2.  **Aplicar Estandar**: Copie el contenido de [[TEMPLATE-CP]] en cada nuevo archivo.
3.  **Establecer Trazabilidad**: Asegurese de que el campo `requerimiento` en el frontmatter apunte correctamente al `[[REQ-XX]]` correspondiente.

### Tarea 5.3: Ejecucion y Registro (DO - Parte 2)
1.  **Preparar Entorno**: Verifique que el sistema esté funcionando y conectado a la base de datos de producción/pruebas.
2.  **Ejecutar Pasos**: Siga el procedimiento definido en el CP y compare el "Resultado Real" con el "Resultado Esperado".
3.  **Documentar Hallazgos**: Si hay una discrepancia, marque el estado como "Fallido" y registre las observaciones técnicas.

### Tarea 5.4: Evaluacion y Mejora (CHECK & ACT)
1.  **Analizar Fallos**: Determine si el fallo es un error de código, un error de diseño o un requerimiento ambiguo.
2.  **Reportar Defectos**: Registre cada fallo en el [[01-Registro_Defectos]].
3.  **Cerrar el Ciclo**: Si un CP falla debido a un requerimiento mal especificado, regrese al [[PROC-02_Especificacion_Requerimientos]] para corregir la base.

## 3. Matriz de Responsabilidades (RACI)

| Tarea | Axel (Tester) | Samuel (QA Lead) | Cliente |
| :--- | :---: | :---: | :---: |
| T5.1 Planificacion | **R** | A | I |
| T5.2 Diseño CP | **R** | C | I |
| T5.3 Ejecucion | **R** | I | I |
| T5.4 Reporte Defectos | **R** | A | C |

*(R: Responsable, A: Aprueba, C: Consultado, I: Informado)*

## 4. Estructura de Casos de Prueba (Referencia)

Para garantizar la estandarización, todos los casos de prueba deben utilizar la plantilla oficial.

- **Plantilla Oficial**: [[TEMPLATE-CP]]

## 5. Casos de Prueba por Modulo (Seguimiento)

## 3. Casos de Prueba por Modulo

### Modulo 1 - Carga de Imagen
| ID | Titulo | REQ | Estado |
| :-- | :-- | :-- | :-- |
| CP-01 | JPG valida | REQ-01 | Pendiente |
| CP-02 | Archivo invalido | REQ-01 | Pendiente |
| CP-03 | Imagen grande | REQ-01 | Pendiente |

### Modulo 2 - Catalogo de Marcos
| ID | Titulo | REQ | Estado |
| :-- | :-- | :-- | :-- |
| CP-04 | Carga catalogo | REQ-04 | Pendiente |
| CP-05 | Filtro modelo | REQ-05 | Pendiente |
| CP-06 | Filtro color | REQ-05 | Pendiente |
| CP-07 | Filtro ancho | REQ-05 | Pendiente |

### Modulo 3 - Previsualizacion
| ID | Titulo | REQ | Estado |
| :-- | :-- | :-- | :-- |
| CP-08 | Marco simple | REQ-02 | Pendiente |
| CP-09 | Marco doble | REQ-07 | Pendiente |
| CP-10 | Tipo vidrio | REQ-08 | Pendiente |
| CP-11 | Maria Luisa | REQ-09 | Pendiente |
| CP-12 | Proporciones | REQ-02 | Pendiente |

### Modulo 4 - Pantalla Secundaria
| ID | Titulo | REQ | Estado |
| :-- | :-- | :-- | :-- |
| CP-13 | Proyeccion | REQ-10 | Pendiente |
| CP-14 | Sync tiempo real | REQ-10 | Pendiente |
| CP-15 | Fallback sin pantalla | REQ-10 | Pendiente |

## 4. Plantilla de Caso de Prueba

```yaml
---
id: CP-XX
titulo: ""
modulo: ""
tipo_prueba: Sistema
requerimiento: ""
version_sistema: "1.0"
estado: Pendiente
entrada: ""
precondiciones: ""
pasos: []
resultado_esperado: ""
resultado_actual: ""
severidad_defecto: ""
fecha_ejecucion: ""
responsable: ""
tags:
  - cp/pendiente
---
```

## 5. Criterios de Aceptacion

- [ ] Plan Maestro de Pruebas creado
- [ ] CP para todos los REQ creados
- [ ] 100% de CP ejecutados
- [ ] Defectos registrados y rastreados
- [ ] Reporte de calidad generado

## 6. Dependencias

- **Pre-requisito**: [[PROC-02_Especificacion_Requerimientos]], [[PROC-04_Arquitectura_Sistema]]
- **Post-requisito**: [[PROC-06_Inspecciones]]

## 7. Referencias

- [[01-Proceso_Gobernanza_Vault]]
- [[01-Registro_Defectos]]

---

*Proceso creado: 2026-03-19*
