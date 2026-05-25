
# INS-02: Inspeccion del Plan de Pruebas
**Responsable:** Analista de Control y Cambios
**Entradas:** Registros de Defectos e Incidentes
**Salidas:** Solicitudes de Cambio Aprobadas e Informes de Inspección

---

## 1. Objetivo

Realizar una inspeccion formal del Plan Maestro de Pruebas y sus casos de prueba para verificar su calidad, cobertura y trazabilidad.

## 2. Alcance

Esta inspeccion cubre:

- [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan de Pruebas]] - Plan general
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
| **Autor** | Analista Técnico | Propietario del plan |
| **Lector 1** | Líder SQA | Revisor principal |
| **Lector 2** | Por asignar | Segundo revisor |
| **Moderador** | Líder SQA | Facilita la reunion |

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

- [[05-Revisiones e inspecciones/01-Ingenieria_Control/05-PROC-05.2_Inspecciones|PROC-09 Inspecciones]]
- [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan de Pruebas]] - Carpeta de pruebas
- [[01-Gestion de la configuracion/03-STD-02_Convenciones_Tags|STD-02 Convenciones y Tags]] - Plantillas de CP

---

*Inspeccion creada: 2026-03-23*
*Proximo paso: Ejecutar inspeccion una vez completado el plan de pruebas*