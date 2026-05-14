---
id: INS-01
titulo: Inspeccion de Requerimientos
version: "1.0"
estado: Pendiente
tipo: Inspeccion
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Samuel Blanco
referencias:
  - SWEBOK v4 KA1 - Requisitos
  - O'Regan - Fagan Inspection
  - PROC-06_Inspecciones
tags:
  - inspeccion
  - requisitos
  - calidad
---

# INS-01: Inspeccion de Requerimientos

## 1. Objetivo

Realizar una inspeccion formal de los requerimientos del proyecto Visualizador de Marcos para verificar su calidad, completitud y consistencia.

## 2. Alcance

Esta inspeccion cubre todos los documentos de requerimientos:

- REQ-01 a REQ-06: Requerimientos implementados
- REQ-07 a REQ-10: Requerimientos pendientes (Scope Creep)

## 3. Criterios de Inspeccion

### 3.1 Criterios de Calidad (IEEE 830)

| Criterio | Descripcion | Peso |
|----------|-------------|------|
| **Completo** | Todos los requisitos del usuario estan definidos | 20% |
| **Consistente** | No hay contradicciones entre requisitos | 20% |
| **Factible** | El requisitos es implementable con tecnologia actual | 15% |
| **Verificable** | Se puede probar que se cumple el requisito | 20% |
| **Rastreable** | Se puede rastrear a origen y diseño | 15% |
| **Modificable** | El documento esta estructurado para facilitar cambios | 10% |

### 3.2 Checklist de Revision

#### Requerimientos Funcionales

- [ ] Cada REQ tiene ID unico
- [ ] Cada REQ tiene titulo descriptivo
- [ ] Cada REQ tiene criterios de aceptacion en formato BDD
- [ ] Cada REQ tiene precondiciones definidas
- [ ] Cada REQ tiene flujos (principal, alternativo, exception)
- [ ] Cada REQ tiene reglas de negocio documentadas

#### Trazabilidad

- [ ] Cada REQ referencia sus casos de prueba (CP)
- [ ] Cada REQ referencing sus Change Requests (CR) si aplica
- [ ] Cada REQ tiene fuente documentada

#### Metadatos (YAML Frontmatter)

- [ ] Todos los REQ tienen id
- [ ] Todos los REQ tienen titulo
- [ ] Todos los REQ tienen version
- [ ] Todos los REQ tienen estado (Borrador/Activo/Pendiente)
- [ ] Todos los REQ tienen prioridad
- [ ] Todos los REQ tienen tipo (Funcional/No-Funcional)
- [ ] Todos los REQ tienen tags apropiados

## 4. Participantes

| Rol | Responsable | Funcion |
|-----|-------------|---------|
| **Autor** | Axel Morales | Propietario de los documentos |
| **Lector 1** | Samuel Blanco | Revisor principal |
| **Lector 2** | Por asignar | Segundo revisor |
| **Moderador** | Samuel Blanco | Facilita la reunion |

## 5. Proceso de Inspeccion

### 5.1 Fases

1. **Planeacion**: Asignar revisores y fecha (2 dias)
2. **Preparacion**: Revisores leen y marcan defectos (5 dias)
3. **Reunion**: Discusion de defectos encontrados (1 hora)
4. **Rework**: Autor corrige defectos (3 dias)
5. **Seguimiento**: Verificar correcciones (1 dia)

### 5.2 Checklist de Entrada

- [ ] Todos los REQ disponibles en vault
- [ ] Version actual de cada documento
- [ ] Acceso para todos los revisores

### 5.3 Checklist de Salida

- [ ] Reporte de defectos generado
- [ ] Defectos clasificados por severidad
- [ ] Plan de correccion definido

## 6. Defectos Esperados

Se anticipan defectos en las siguientes areas:

- Requerimientos faltantes (Scope)
- Criterios de aceptacion ambiguos
- Inconsistencias entre REQ
- Falta de trazabilidad

## 7. Referencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/PROC-06_Inspecciones]]
- [[02-Requerimientos/]] - Carpeta de requerimientos
- [[02-Convenciones_y_Tags]] - Estandares de documentacion

---

*Inspeccion creada: 2026-03-23*
*Proximo paso: Ejecutar inspeccion una vez completados los REQ*