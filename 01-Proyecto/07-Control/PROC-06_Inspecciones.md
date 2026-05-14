---
id: PROC-06
titulo: Proceso 6 - Inspecciones de Calidad
version: "1.0"
estado: Pendiente
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-03-19
responsable: Samuel Blanco
disparador: Finalizacion de fase o deliverable
criterio_entrada: Artefacto listo para revision
criterio_salida: Informe de inspeccion con hallazgos
entradas:
  - Requerimientos especificados
  - Plan de pruebas
  - Documentos de arquitectura
salidas:
  - INS-01_Informe_Inspeccion_Requerimientos.md
  - INS-02_Informe_Inspeccion_Plan_Pruebas.md
actividades:
  - Preparar el material para inspeccion
  - Conformar el equipo de inspeccion
  - Realizar la inspeccion (walkthrough o inspection formal)
  - Documentar hallazgos
  - Realizar seguimiento de acciones correctivas
roles:
  - Lider de inspeccion
  - Inspectores (2-4 personas)
  - Autor del artefacto
referencias_biblio:
  - "O'Regan Cap. 2 - Inspecciones Fagan"
  - "SWEBOK v4 KA8 - Procesos de Calidad"
tags:
  - proceso
  - inspeccion
  - calidad
---

# Proceso 6 — Inspecciones de Calidad

> **Justificacion**: Segun O'Regan, "las inspecciones son una de las tecnicas mas efectivas para la deteccion temprana de defectos". Las inspecciones Fagan, en particular, siguen un proceso riguroso con fases de planificacion, introduccion, preparacion, reunion de inspeccion y seguimiento. SWEBOK v4 enfatiza que las inspecciones deben ser parte integral del proceso de desarrollo.

## 1. Definicion del Proceso

| Campo | Descripcion |
| :-- | :-- |
| **Disparador** | Finalizacion de fase o deliverable. Necesario porque las inspecciones deben aplicarse sobre artefactos terminados para detectar defectos antes de avanzar al siguiente proceso. (O'Regan Cap. 2) |
| **Criterio de Entrada** | Artefacto listo para revision. Se usa para aplicar tecnicas de inspeccion Fagan: planificacion, preparacion, reunion y seguimiento de acciones correctivas. |
| **Actividades** | Ver lista abajo |
| **Salida / Entregable** | Informe de inspeccion con hallazgos. Proporciona evidencia de revision formal y registro de defectos detectados tempranamente. (SWEBOK v4 KA8) |
| **Responsable** | Samuel Blanco (lider SQA) |
| **Criterio de Salida** | Informe de inspeccion aprobado, acciones correctivas definidas y verificadas. |

## 2. Actividades del Proceso (Ciclo de Inspeccion Fagan)

### Fase 1: Planificacion
1. Identificar el artefacto a inspeccionar.
2. Seleccionar el equipo de inspeccion.
3. Programar la reunion.
4. Asignar roles.

### Fase 2: Introduccion
5. Presentar el contexto y objetivos al equipo.
6. Explicar el proceso de inspeccion.

### Fase 3: Preparacion
7. Cada inspector revisa el artefacto individualmente.
8. Se identifican potenciales defectos.
9. Se documentan los hallazgos.

### Fase 4: Reunion de Inspeccion
10. El autor presenta el artefacto.
11. Se discuten los hallazgos.
12. Se clasifican los defectos.
13. Se definen acciones correctivas.

### Fase 5: Seguimiento
14. El autor corrige los defectos.
15. Se verifica la correccion.
16. Se cierra la inspeccion.

## 3. Tipos de Inspeccion

### 3.1 Walkthrough (Revision Informal)
- Participantes: Autor + 1-2 colegas
- Objetivo: Revision rapida
- Sin proceso formal

### 3.2 Inspection (Revision Formal)
- Participantes: Lider + 2-4 inspectores + Autor
- Objetivo: Deteccion rigurosa de defectos
- Proceso formal con documentacion

## 4. Plantilla de Informe de Inspeccion

```markdown
# Informe de Inspeccion - [Nombre del Artefacto]

## 1. Informacion General
| Campo | Valor |
| :-- | :-- |
| ID Inspeccion | INS-XX |
| Artefacto | [Nombre y ruta] |
| Version | X.X |
| Fecha | YYYY-MM-DD |
| Lider | [Nombre] |

## 2. Equipo de Inspeccion
| Rol | Nombre |
| :-- | :-- |
| Lider | [Nombre] |
| Inspector 1 | [Nombre] |
| Inspector 2 | [Nombre] |
| Autor | [Nombre] |

## 3. Hallazgos

### 3.1 Defectos Criticos
| ID | Descripcion | Linea | Responsable |
| :-- | :-- | :-- | :-- |
| D-01 | [Descripcion] | [Numero] | [Nombre] |

### 3.2 Defectos Menores
| ID | Descripcion | Linea | Responsable |
| :-- | :-- | :-- | :-- |
| D-02 | [Descripcion] | [Numero] | [Nombre] |

### 3.3 Observaciones
| ID | Descripcion |
| :-- | :-- |
| O-01 | [Observacion] |

## 4. Acciones Correctivas
| ID | Accion | Responsable | Fecha Limite |
| :-- | :-- | :-- | :-- |
| AC-01 | [Accion] | [Nombre] | YYYY-MM-DD |

## 5. Resultados
| Criterio | Resultado |
| :-- | :-- |
| Total Defectos | [Numero] |
| Defectos Cerrados | [Numero] |
| Estado | [Aprobado/Rechazado/Condicional] |

## 6. Firmas de Aprobacion
- Lider de Inspeccion: _________________ Fecha: _______
- Autor: _________________ Fecha: _______
```

## 5. Criterios de Aceptacion del Proceso

- [ ] Inspeccion de Requerimientos completada
- [ ] Inspeccion de Plan de Pruebas completada
- [ ] Informe de inspeccion aprobado
- [ ] Acciones correctivas implementadas
- [ ] Proceso cerrado con estado = "Completado"

## 6. Dependencias

- **Pre-requisito**: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/PROC-02_Especificacion_Requerimientos]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/PROC-05_Plan_Pruebas]]
- **Post-requisito**: Ninguno (proceso final)

## 7. Referencias

- [[01-Proceso_Gobernanza_Vault]]
- [[02-Convenciones_y_Tags]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/INS-01_Inspeccion_Requerimientos]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/INS-02_Inspeccion_Plan_Pruebas]]

---

*Proceso creado: 2026-03-19 | Ultima actualizacion: 2026-03-19*
