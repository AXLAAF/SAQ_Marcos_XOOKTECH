---
id: INS-02
titulo: Inspeccion del Plan de Pruebas
version: "1.0"
estado: Pendiente
tipo: Inspeccion
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Samuel Blanco
referencias:
  - SWEBOK v4 KA5 - Testing
  - Lewis - Testing and Quality
  - PROC-06_Inspecciones
tags:
  - inspeccion
  - pruebas
  - calidad
---

# INS-02: Inspeccion del Plan de Pruebas

## 1. Objetivo

Realizar una inspeccion formal del Plan Maestro de Pruebas y sus casos de prueba para verificar su calidad, cobertura y trazabilidad.

## 2. Alcance

Esta inspeccion cubre:

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]] - Plan general
- Casos de prueba CP-01 a CP-15
- Matriz de trazabilidad REQ -> CP

## 3. Criterios de Inspeccion

### 3.1 Criterios de Calidad del Plan de Pruebas

| Criterio | Descripcion |
|----------|-------------|
| **Completo** | Todos los modulos tienen casos de prueba |
| **Ejecutable** | Cada CP tiene datos de prueba definidos |
| **Trazable** | Cada REQ tiene al menos un CP asociado |
| **Cubridor** | Cover todos los criterios de aceptacion |
| **Actualizado** | Refleja el estado actual del sistema |

### 3.2 Checklist de Revision del Plan

- [ ] Alcance claramente definido
- [ ] Tipos de prueba especificados
- [ ] Criterios de entrada y salida definidos
- [ ] Recursos asignados
- [ ] Schedule realista
- [ ] Gestion de defectos documentada

### 3.3 Checklist de Revision de Casos de Prueba

Para cada CP verificar:

- [ ] ID unico y descriptivo
- [ ] Modulo y tipo de prueba
- [ ] Requerimiento asociado
- [ ] Estado (Pendiente/Ejecutado)
- [ ] Datos de prueba definidos
- [ ] Precondiciones claras
- [ ] Pasos numerados
- [ ] Resultado esperado definido
- [ ] Criterios de exito listed

### 3.4 Checklist de Trazabilidad

- [ ] Cada REQ tiene al menos un CP
- [ ] Cada CP referencia su REQ
- [ ] Scope Creep (REQ-07 a REQ-10) tiene sus CP asignados
- [ ] Matriz REQ -> CP -> CR esta completa

## 4. Matriz de Cobertura Esperada

| REQ | CP Asociados | Cobertura |
|-----|--------------|-----------|
| REQ-01 | CP-01, CP-02, CP-03 | 100% |
| REQ-02 | CP-08, CP-12 | 100% |
| REQ-03 | CP-08 | 100% |
| REQ-04 | CP-04 | 100% |
| REQ-05 | CP-05, CP-06, CP-07 | 100% |
| REQ-06 | CP-04 | 100% |
| REQ-07 | CP-09 | 100% (Pendiente) |
| REQ-08 | CP-10 | 100% (Pendiente) |
| REQ-09 | CP-11 | 100% (Pendiente) |
| REQ-10 | CP-13, CP-14, CP-15 | 100% (Pendiente) |

## 5. Participantes

| Rol | Responsable | Funcion |
|-----|-------------|---------|
| **Autor** | Axel Morales | Propietario del plan |
| **Lector 1** | Samuel Blanco | Revisor principal |
| **Lector 2** | Por asignar | Segundo revisor |
| **Moderador** | Samuel Blanco | Facilita la reunion |

## 6. Proceso de Inspeccion

### 6.1 Fases

1. **Planeacion**: Asignar revisores (1 dia)
2. **Preparacion**:Revision individual (3 dias)
3. **Reunion**: Discusion de hallazgos (1 hora)
4. **Rework**: Actualizar CP segun feedback (2 dias)
5. **Seguimiento**: Verificar correcciones

### 6.2 Checklist de Entrada

- [ ] Plan Maestro disponible
- [ ] 15 CP completados
- [ ] Matriz de trazabilidad generada

### 6.3 Checklist de Salida

- [ ] Informe de cobertura generado
- [ ] Defectos de prueba documentados
- [ ] Plan de mejora definido

## 7. Defectos Tipicos Esperados

- Casos de prueba con pasos vagos
- Datos de prueba faltantes
- Resultados esperados ambiguos
- CP sin precondiciones
- Falta de trazabilidad

## 8. Referencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/PROC-06_Inspecciones]]
- [[05-Pruebas/]] - Carpeta de pruebas
- [[02-Convenciones_y_Tags]] - Plantillas de CP

---

*Inspeccion creada: 2026-03-23*
*Proximo paso: Ejecutar inspeccion una vez completado el plan de pruebas*