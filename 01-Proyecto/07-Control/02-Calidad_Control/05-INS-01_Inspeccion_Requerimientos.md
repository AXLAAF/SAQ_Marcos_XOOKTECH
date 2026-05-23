
# INS-01: Inspeccion de Requerimientos
**Responsable:** Analista de Control y Cambios
**Entradas:** Registros de Defectos e Incidentes
**Salidas:** Solicitudes de Cambio Aprobadas e Informes de Inspección

---

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
| **Autor** | Analista Técnico | Propietario de los documentos |
| **Lector 1** | Líder SQA | Revisor principal |
| **Lector 2** | Por asignar | Segundo revisor |
| **Moderador** | Líder SQA | Facilita la reunion |

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

- [[07-Control/01-Ingenieria_Control/04-PROC-09_Inspecciones|PROC-09 Inspecciones]]
- [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03 Matriz de Trazabilidad]] - Carpeta de requerimientos
- [[00-Meta/03-STD-02_Convenciones_Tags|STD-02 Convenciones y Tags]] - Estandares de documentacion

---

*Inspeccion creada: 2026-03-23*
*Proximo paso: Ejecutar inspeccion una vez completados los REQ*