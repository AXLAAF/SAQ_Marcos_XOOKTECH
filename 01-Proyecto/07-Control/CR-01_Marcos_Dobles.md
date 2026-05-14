---
id: CR-01
titulo: Change Request - Marcos Dobles
estado: Pendiente
tipo_cambio: Nuevo-Requerimiento
requerimiento_origen: REQ-07_Marcos_Dobles
solicitado_por: Cliente (Enmarcame - Geronimo)
fecha_solicitud: 2026-01-15
descripcion: El cliente solicito la funcionalidad para que el sistema soporte marcos dobles (dos fotografias o dos espacios para fotos en un mismo marco).
impacto_tiempo_dias: 5
impacto_costo_mxn: 3000
aprobado_por: ""
fecha_aprobacion: ""
casos_prueba_requeridos:
  - CP-09_Marco_doble
referencias:
  - REQ-07_Marcos_Dobles
  - "01-Baseline/02-Acuerdos_Cliente.md - ACU-006"
tags:
  - cr/pendiente
  - scope-creep
---

# CR-01: Marcos Dobles

## 1. Informacion del Cambio

| Campo | Valor |
|-------|-------|
| **ID** | CR-01 |
| **Fecha de Solicitud** | 2026-01-15 |
| **Solicitado por** | Cliente (Enmarcame - Geronimo) |
| **Tipo de Cambio** | Nuevo Requerimiento |
| **Estado** | Pendiente de Aprobacion |

## 2. Descripcion del Cambio

### 2.1 Problema/Necesidad del Cliente

El cliente atiende frecuentemente clientes que desean enmarcar dos fotografias juntas (por ejemplo, fotos de bodas, anniversarios, o fotos familiares). Actualmente el sistema solo soporta un marco para una fotografia, lo cual limita estas ventas.

### 2.2 Requerimiento Asociado

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-07_Marcos_Dobles]] - Requerimiento funcional asociado

### 2.3 Descripcion Tecnica

El sistema debe permitir:
- Seleccionar un marco doble que tenga dos espacios para fotografias
- Cargar dos imagenes diferentes (una para cada espacio)
- Ver la previsualizacion de ambas fotografias en el marco doble
- Ajustar individualmente tamano y posicion de cada foto

## 3. Impacto del Cambio

### 3.1 Impacto en Tiempo

| Actividad | Dias Estimados |
|-----------|----------------|
| Desarrollo frontend | 2 |
| Desarrollo backend | 1 |
| Pruebas | 1 |
| Documentacion | 1 |
| **Total** | **5 dias** |

### 3.2 Impacto en Costo

| Concepto | Monto (MXN) |
|----------|-------------|
| Desarrollo | $2,500 |
| Pruebas | $500 |
| **Total** | **$3,000** |

> **Nota**: Este costo NO esta incluido en el acuerdo original de $24,000 MXN. Es un cargo adicional por Scope Creep.

## 4. Analisis de Riesgo

| Riesgo | Probabilidad | Impacto | Mitigacion |
|--------|--------------|---------|------------|
| Afecta funcionalidad de marcos simples | Baja | Alto | Pruebas de regresion extensivas |
| Requiere actualizacion de base de datos | Media | Medio | Backup antes del cambio |
| Compatibilidad con dispositivos existentes | Baja | Medio | Pruebas en multiples navegadores |

## 5. Criterios de Aceptacion del Cambio

- [ ] El cliente aprueba formalmente el costo adicional de $3,000 MXN
- [ ] Se define una fecha de entrega acordada
- [ ] Se documenta el alcance en un addendum al acuerdo original
- [ ] El equipo de desarrollo confirma el estimado de 5 dias

## 6. Aprobacion

| Campo | Valor |
|-------|-------|
| Elaborado por | Axel Adolfo Morales Caro |
| Fecha de elaboracion | 2026-03-23 |
| Estado | Pendiente de aprobacion |

### Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-03-23 | Axel Morales | Creacion inicial del CR |

---

*Change Request creado como parte del proceso de control de cambios (PROC-03)*
*Referencia: [[02-Acuerdos_Cliente]] - ACU-006*
*Este cambio requiere aprobacion formal del cliente antes de proceder*