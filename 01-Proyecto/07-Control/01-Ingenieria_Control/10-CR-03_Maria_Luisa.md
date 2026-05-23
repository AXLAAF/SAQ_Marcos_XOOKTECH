
# CR-03: Maria Luisa Multiple
**Responsable:** Analista de Control y Cambios
**Entradas:** Registros de Defectos e Incidentes
**Salidas:** Solicitudes de Cambio Aprobadas e Informes de Inspección

---

> Registro alineado con [[00-Meta/99-Plantillas_y_Checklists/TEMPLATE-CR]].

## 1. Informacion del Cambio

| Campo | Valor |
|-------|-------|
| **ID** | CR-03 |
| **Fecha de Solicitud** | 2026-01-25 |
| **Solicitado por** | Cliente (Enmarcame - Cliente) |
| **Tipo de Cambio** | Nuevo Requerimiento |
| **Estado** | Pendiente de Aprobacion |

## 2. Descripcion del Cambio

### 2.1 Problema/Necesidad del Cliente

La Maria Luisa es un marco decorativo interno que rodea la fotografia. El negocio tiene varios diseños de Maria Luisa disponibles, pero actualmente el sistema solo permite usar una por defecto. Los clientes frecuentemente preguntan por alternativas.

### 2.2 Requerimiento Asociado

- [[02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/09-REQ-09_Maria_Luisa|REQ-09 María Luisa]] - Requerimiento funcional asociado

### 2.3 Descripción Técnica

El sistema debe permitir:
- Mostrar un catalogo de Maria Luisas disponibles
- Permitir seleccionar la Maria Luisa junto con el marco
- Previsualizar la combinación ( marco + Maria Luisa + foto )
- Incluir la Maria Luisa seleccionada en la orden final

## 3. Impacto del Cambio

### 3.1 Impacto en Tiempo

| Actividad | Dias Estimados |
|-----------|----------------|
| Desarrollo frontend | 1.5 |
| Desarrollo backend | 1 |
| Escaneo de Maria Luisas | 0.5 |
| Pruebas | 0.5 |
| Documentacion | 0.5 |
| **Total** | **4 dias** |

### 3.2 Impacto en Costo

| Concepto | Monto (MXN) |
|----------|-------------|
| Desarrollo | $1,800 |
| Escaneo de Maria Luisas | $200 |
| Pruebas | $500 |
| **Total** | **$2,500** |

> **Nota**: Este costo NO esta incluido en el acuerdo original de $24,000 MXN. Es un cargo adicional por Scope Creep.

## 4. Analisis de Riesgo

| Riesgo | Probabilidad | Impacto | Mitigacion |
|--------|--------------|---------|------------|
| Afecta previsualizacion 3D | Media | Alto | Pruebas de renderizado con diferentes combinaciones |
| Requiere escaneo de catalogo | Baja | Medio | Ya se tiene algunos diseños escaneados |
| Complejidad de combinatoria | Media | Medio | Limitar a combinaciones validas |

## 5. Criterios de Aceptacion del Cambio

- [ ] El cliente aprueba formalmente el costo adicional de $2,500 MXN
- [ ] Se define una fecha de entrega acordada
- [ ] Se documenta el alcance en un addendum al acuerdo original
- [ ] El equipo de desarrollo confirma el estimado de 4 dias

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
*Referencia: [[01-Linea_Base/03-Acuerdos_Cliente|Acuerdos con el Cliente]] - ACU-008*
*Este cambio requiere aprobacion formal del cliente antes de proceder*
*Prioridad: Media - Ya se tienen algunos diseños escaneados*