---
id: PROC-03
titulo: Proceso 3 - Control de Cambios (CR)
version: "1.0"
estado: Pendiente
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-04-13
responsable: Samuel Blanco
disparador: Solicitud de cambio por parte del cliente o equipo
criterio_entrada: Solicitud formal de cambio recibida
criterio_salida: Change Request evaluado, aprobado/rechazado y documentado
entradas:
  - Solicitud de cambio verbal o escrita
  - Requerimientos afectados
  - Estimacion de impacto
salidas:
  - CR-XX_Nombre.md (Change Request)
  - Actualizacion de REQ afectado
  - Plan de implementacion (si aprobado)
actividades:
  - Registrar la solicitud de cambio
  - Evaluar impacto en alcance, tiempo, costo y calidad
  - Crear el Change Request formal
  - Presentar al cliente para aprobacion
  - Actualizar el alcance y requisitos si es aprobado
  - Notificar al equipo de desarrollo
roles:
  - Samuel Blanco (analista de negocio)
  - Axel Morales (analista tecnico)
  - Cliente (aprobador)
referencias_biblio:
  - "SWEBOK v4 KA1 6.2 - Control de Cambios"
  - "Lewis Cap. 21-25 - Gestion de cambios y scope creep"
  - "O'Regan Cap. 3 - Control de Calidad"
tags:
  - proceso
  - control-cambios
---

# Proceso 3 — Control de Cambios (Change Requests)

> **Justificacion**: Segun SWEBOK v4 KA1 §6.2, "el control de cambios es el proceso de gestionar las solicitudes de cambio al software, evaluando su impacto y decidiendo que acciones tomar". Lewis enfatiza que el "scope creep" (expansion descontrolada del alcance) es una de las principales causas de falla en proyectos de software, y el control de cambios es la defensa principal contra este riesgo.

## 1. Definicion del Proceso

| Campo | Descripcion |
| :-- | :-- |
| **Disparador** | Solicitud de cambio por parte del cliente o equipo. Necesario para gestionar scope creep y mantener control sobre el proyecto. (Lewis Cap. 21) |
| **Criterio de Entrada** | Solicitud formal de cambio recibida. Se usa para iniciar evaluacion de impacto antes de implementar cambios no planificados. (O'Regan Cap. 3) |
| **Actividades** | Ver lista abajo |
| **Salida / Entregable** | CR documentado, evaluado y con decision tomada. Proporciona trazabilidad para cambios aprobados, facilitando auditorias. (SWEBOK v4 KA1 6.2) |
| **Responsable** | Samuel Blanco (analista) + Cliente (aprobador) |
| **Criterio de Salida** | Change Request con estado: Aprobado, Rechazado o En_Analisis. Documentacion actualizada. [PENDIENTE - confirmar con Samuel si se requiere aprobacion escrita para todos los CR.] |

## 2. Actividades del Proceso

1. Registrar la solicitud de cambio en el formato de CR. (Documenta formalmente para trazabilidad, previniendo disputas futuras. SWEBOK v4 KA1 6.2) -> Artefacto: [[CR-XX_Nombre]]
2. Analizar el impacto en alcance, tiempo, costo y calidad. (Evalua consecuencias para decision informada, evitando overruns. Lewis Cap. 22)
3. Evaluar dependencias con otros requerimientos. (Identifica efectos en cadena para planificacion completa. O'Regan Cap. 3)
4. Crear el Change Request formal en el vault. (Estandariza documentacion para revision y aprobacion. SWEBOK v4 KA1 6.2)
5. Presentar al cliente con la estimacion de impacto. (Transparencia para decision conjunta, reduciendo conflictos. Lewis Cap. 23)
6. Obtener aprobacion formal por escrito. (Protege partes legalmente, evita malentendidos. O'Regan Cap. 1)
7. Si es aprobado: actualizar el REQ correspondiente y crear plan de implementacion. (Integra cambio al alcance controlado. SWEBOK v4 KA1 6.2) -> Artefacto: [[REQ-XX_Nombre]]
8. Si es rechazado: documentar la razon y cerrar el CR. (Cierra ciclo con explicacion, para aprendizaje. Lewis Cap. 24)
9. Notificar al equipo de desarrollo. (Coordina implementacion, asegurando alineacion. SWEBOK v4 KA3)

## 3. Plantilla de Change Request

Esta seccion describe la plantilla para CR. La aplicacion completa con ejemplos se encuentra en cada [[CR-XX_Nombre]]. La plantilla asegura evaluacion completa de impacto para decisiones fundamentadas. (SWEBOK v4 KA1 6.2 - Control de Cambios)

```yaml
---
id: CR-XX
titulo: ""
estado: Pendiente
tipo_cambio: Nuevo-Requerimiento
requerimiento_origen: ""
solicitado_por: ""
fecha_solicitud: YYYY-MM-DD
descripcion: ""
impacto_tiempo_dias: 0
impacto_costo_mxn: 0
aprobado_por: ""
fecha_aprobacion: ""
casos_prueba_requeridos: []
tags:
  - cr/pendiente
---
```

### Seccion de Documentacion del CR

```markdown
# CR-[ID]: [Titulo del Cambio]

## 1. Informacion General
| Campo | Valor |
| :-- | :-- |
| ID | CR-XX |
| Titulo | [Nombre del cambio] |
| Estado | [Pendiente/En_Analisis/Aprobado/Rechazado] |
| Tipo de Cambio | [Nuevo-Requerimiento/Modificacion/Eliminacion] |
| Fecha de Solicitud | YYYY-MM-DD |
| Solicitado por | [Nombre] |

## 2. Descripcion del Cambio
[Descripcion detallada de lo que se esta solicitando]

## 3. Justificacion
[Razon por la cual se necesita este cambio]

## 4. Requerimiento Origen
[Si este cambio modifica un requerimiento existente, linkearlo]
- REQ-XX: [[REQ-XX_Titulo]]

## 5. Analisis de Impacto

### 5.1 Impacto en Alcance
- [Lista de requerimientos afectados]

### 5.2 Impacto en Tiempo
- Dias adicionales estimados: X

### 5.3 Impacto en Costo
- Costo adicional estimado: $X,XXX MXN

### 5.4 Impacto en Calidad
- [Efectos potenciales en la calidad]

### 5.5 Dependencias
- [Otros cambios o requerimientos relacionados]

## 6. Casos de Prueba Requeridos
- [Lista de CP que necesitan ser creados o modificados]

## 7. Decision

### 7.1 Aprobacion (si aplica)
| Campo | Valor |
| :-- | :-- |
| Aprobado por | [Nombre del cliente] |
| Fecha de Aprobacion | YYYY-MM-DD |
| Notas | [Notas adicionales] |

### 7.2 Rechazo (si aplica)
| Campo | Valor |
| :-- | :-- |
| Razon del Rechazo | [Explicacion] |
| Fecha | YYYY-MM-DD |

## 8. Historial de Versiones
| Version | Fecha | Autor | Cambios |
| :-- | :-- | :-- | :-- |
| 1.0 | YYYY-MM-DD | [Nombre] | Creacion inicial |
```

## 4. Cambios Actuales Registrados

| ID | Titulo | Estado | Origen | Impacto Estimado |
| :-- | :-- | :-- | :-- | :-- |
| CR-01 | Marcos Dobles | Pendiente | REQ-07 | Por definir |
| CR-02 | Tipos de Vidrio | Pendiente | REQ-08 | Por definir |
| CR-03 | Maria Luisa Multiple | Pendiente | REQ-09 | Por definir |
| CR-04 | Pantalla Secundaria | Pendiente | REQ-10 | Por definir |

## 5. Tipos de Cambio

| Tipo | Descripcion | Ejemplo |
| :-- | :-- | :-- |
| Nuevo-Requerimiento | Agregar funcionalidad nueva | Agregar soporte para marcos dobles |
| Modificacion | Cambiar alcance de requerimiento existente | Modificar tamano maximo de imagen |
| Eliminacion | Quitar funcionalidad acordada | Eliminar modulo de exportacion PDF |
| Correccion | Corregir error en requerimiento | Aclarar criterio de aceptacion ambiguo |

## 6. Criterios de Aprobacion

Para aprobar un Change Request, deben cumplirse:

- [ ] Impacto en tiempo documentado y aceptado
- [ ] Impacto en costo documentado y aceptado
- [ ] Cliente ha dado aprobacion escrita
- [ ] Casos de prueba actualizados o creados
- [ ] Requerimientos afectados actualizados

## 7. Criterios de Aceptacion del Proceso

- [ ] Todos los CR pendientes documentados
- [ ] Analisis de impacto completado para cada CR
- [ ] Aprobacion del cliente obtenida para CR-01 a CR-04
- [ ] Requerimientos actualizados si hay cambios aprobados
- [ ] Proceso cerrado con estado = "Completado"

## 8. Dependencias

- **Pre-requisito**: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/PROC-02_Especificacion_Requerimientos]] (Proporciona REQ especificados para evaluar cambios)
- **Post-requisito**: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/PROC-05_Plan_Pruebas]] (Crea CP para cambios aprobados)

## 9. Referencias

- [[01-Proceso_Gobernanza_Vault]]
- [[02-Convenciones_y_Tags]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-01_Marcos_Dobles]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-02_Tipos_Vidrio]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-03_Maria_Luisa]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/CR-04_Pantalla_Secundaria]]

## 10. Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-03-19 | Samuel Blanco | Creacion inicial |
| 1.1 | 2026-04-13 | Kilo-SQA-Agent | Agregadas justificaciones WHY/HOW en definicion, actividades y dependencias |

---

*Proceso creado: 2026-03-19 | Ultima actualizacion: 2026-03-19*
