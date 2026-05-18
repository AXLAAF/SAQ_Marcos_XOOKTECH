---
id: CL-02
titulo: Checklist de Verificacion de Requerimientos
version: "2.0"
estado: Activo
tipo: Checklist
artefacto_objetivo: REQ-XXX_Nombre.md
umbral_aceptacion: "90% total y 100% en items criticos"
---

# CL-02 - Verificacion de Requerimientos

Use este checklist antes de validar un `REQ` con el cliente. Si falla un item critico o el porcentaje total es menor al umbral, el requerimiento debe corregirse antes de pasar a linea base.

## 1. Datos de Evaluacion

| Campo | Valor |
| :-- | :-- |
| Requerimiento evaluado | [REQ-XXX_Nombre] |
| Ruta | [Proyecto/02-Requisitos/.../REQ-XXX_Nombre.md] |
| Evaluador | [Nombre] |
| Fecha | [YYYY-MM-DD] |
| Resultado | [Aprobado / Requiere_Retrabajo] |

## 2. Checklist

### 2.1 Identificacion y contexto

- [ ] **Critico** - El `REQ` tiene ID unico, titulo claro, estado, prioridad y responsable.
- [ ] La fuente del requerimiento esta identificada con documento o evidencia rastreable.
- [ ] El objetivo de negocio explica por que el requerimiento existe y que valor aporta.

### 2.2 Calidad de la especificacion

- [ ] **Critico** - La descripcion general expresa una sola necesidad principal y evita ambiguedad.
- [ ] **Critico** - Las reglas de negocio estan numeradas y son medibles.
- [ ] El alcance incluido y no incluido esta delimitado para evitar interpretaciones fuera de alcance.
- [ ] El flujo principal describe la interaccion esperada de principio a fin.
- [ ] Existen flujos alternativos o de excepcion cuando el escenario lo requiere.
- [ ] Las restricciones tecnicas o de calidad reflejan limites reales del sistema.

### 2.3 Verificabilidad y prueba

- [ ] **Critico** - Los criterios BDD son objetivos, observables y pueden ejecutarse como prueba.
- [ ] Existe relacion con al menos un caso de prueba o una nota de no aplicacion justificada.
- [ ] Las precondiciones permiten reproducir el escenario sin asumir conocimiento implicito.

### 2.4 Trazabilidad y control de cambios

- [ ] **Critico** - El `REQ` referencia el `CR` asociado cuando proviene de un cambio aprobado.
- [ ] La trazabilidad hacia diseno, pruebas y fuente esta registrada o declarada como pendiente controlada.
- [ ] El historial de cambios esta actualizado con la ultima revision.

### 2.5 Validacion lista para cliente

- [ ] El lenguaje del documento es comprensible para negocio y desarrollo.
- [ ] No existen contradicciones con acuerdos previos o con requerimientos ya aprobados.
- [ ] El espacio para evidencia de validacion esta preparado antes de presentar al cliente.

## 3. Calculo del Resultado

| Concepto | Valor |
| :-- | :-- |
| Total de items | 16 |
| Items cumplidos | [Numero] |
| Porcentaje | [Numero]% |
| Items criticos incumplidos | [Lista o N/A] |

Regla de aceptacion:

- Aprobado: 90% o mas de cumplimiento y cero fallas en items criticos.
- Requiere retrabajo: menos de 90% o al menos una falla critica.

## 4. Hallazgos y Accion Correctiva

| ID | Hallazgo | Severidad | Accion requerida | Responsable | Fecha compromiso |
| :-- | :-- | :-- | :-- | :-- | :-- |
| H-01 | [Describa el defecto] | [Alta / Media / Baja] | [Correcion requerida] | [Nombre] | [YYYY-MM-DD] |

## 5. Cierre

- Firma o confirmacion del evaluador: ____________________
- Firma o confirmacion del autor: ____________________
- Fecha de cierre: ____________________
