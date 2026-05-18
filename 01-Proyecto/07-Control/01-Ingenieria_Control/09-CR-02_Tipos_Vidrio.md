
# CR-02: Tipos de Vidrio

> Registro alineado con [[00-Meta/99-Plantillas_y_Checklists/TEMPLATE-CR]].

## 1. Informacion del Cambio

| Campo | Valor |
|-------|-------|
| **ID** | CR-02 |
| **Fecha de Solicitud** | 2026-01-20 |
| **Solicitado por** | Cliente (Enmarcame - Cliente) |
| **Tipo de Cambio** | Nuevo Requerimiento |
| **Estado** | Pendiente de Aprobacion |

## 2. Descripcion del Cambio

### 2.1 Problema/Necesidad del Cliente

El cliente ofrece diferentes tipos de vidrio para proteger los marcos (normal, antirreflejo, templado). Actualmente el sistema no refleja esta opcion, lo cual genera confusion en los clientes que preguntan por las alternativas disponibles.

### 2.2 Requerimiento Asociado

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-08_Tipo_Vidrio]] - Requerimiento funcional asociado

### 2.3 Descripcion Tecnica

El sistema debe permitir:
- Seleccionar el tipo de vidrio desde la interfaz de previsualizacion
- Mostrar una descripcion de cada tipo de vidrio y su precio adicional
- Incluir el tipo de vidrio seleccionado en la orden final
- Tipos de vidrio disponibles:
  - Vidrio normal (estandar)
  - Vidrio antirreflejo (+$150 MXN)
  - Vidrio templado (+$250 MXN)

## 3. Impacto del Cambio

### 3.1 Impacto en Tiempo

| Actividad | Dias Estimados |
|-----------|----------------|
| Desarrollo frontend | 1 |
| Desarrollo backend | 1 |
| Pruebas | 0.5 |
| Documentacion | 0.5 |
| **Total** | **3 dias** |

### 3.2 Impacto en Costo

| Concepto | Monto (MXN) |
|----------|-------------|
| Desarrollo | $1,500 |
| Pruebas | $500 |
| **Total** | **$2,000** |

> **Nota**: Este costo NO esta incluido en el acuerdo original de $24,000 MXN. Es un cargo adicional por Scope Creep.

## 4. Analisis de Riesgo

| Riesgo | Probabilidad | Impacto | Mitigacion |
|--------|--------------|---------|------------|
| Afecta calculo de precios | Baja | Alto | Pruebas exhaustivas de precios |
| Requiere actualizacion de catalogo | Media | Medio | Agregar campo a tabla de productos |
| Interfaz confuse al usuario | Baja | Medio | Diseno intuitivo con tooltips |

## 5. Criterios de Aceptacion del Cambio

- [ ] El cliente aprueba formalmente el costo adicional de $2,000 MXN
- [ ] Se define una fecha de entrega acordada
- [ ] Se documenta el alcance en un addendum al acuerdo original
- [ ] El equipo de desarrollo confirma el estimado de 3 dias

## 6. Aprobacion

| Campo | Valor |
|-------|-------|
| Elaborado por | Analista Técnico |
| Fecha de elaboracion | 2026-03-23 |
| Estado | Pendiente de aprobacion |

### Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-03-23 | Analista Técnico | Creacion inicial del CR |

---

*Change Request creado como parte del proceso de control de cambios (PROC-03)*
*Referencia: [[02-Acuerdos_Cliente]] - ACU-007*
*Este cambio requiere aprobacion formal del cliente antes de proceder*
*Prioridad: Media - Funcionalidad util pero no critica*
