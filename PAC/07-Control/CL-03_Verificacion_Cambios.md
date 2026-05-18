---
id: CL-03
titulo: Checklist de Verificacion de Control de Cambios
version: "1.0"
estado: Activo
tipo: Checklist
artefacto_objetivo: CR-XX_Nombre.md
umbral_aceptacion: "90% total y 100% en items criticos"
---

# CL-03 - Verificacion de Change Requests

Use este checklist antes de solicitar aprobacion del cliente y al cierre del cambio. El `CR` solo puede avanzar si cumple el umbral definido y no falla ningun item critico.

## 1. Datos de Evaluacion

| Campo | Valor |
| :-- | :-- |
| Change Request evaluado | [CR-XX_Nombre] |
| Ruta | [Proyecto/07-Control/CR-XX_Nombre.md] |
| Evaluador | [Nombre] |
| Fecha | [YYYY-MM-DD] |
| Momento de aplicacion | [Previo a aprobacion / Previo a cierre] |
| Resultado | [Aprobado / Requiere_Retrabajo] |

## 2. Checklist

### 2.1 Identificacion del cambio

- [ ] **Critico** - El `CR` tiene ID unico, titulo claro, estado, prioridad y tipo de cambio.
- [ ] **Critico** - El origen de la solicitud y el solicitante estan identificados.
- [ ] La descripcion del cambio explica claramente la necesidad y el comportamiento esperado.

### 2.2 Analisis de impacto

- [ ] **Critico** - El impacto en alcance esta descrito y nombra artefactos o modulos afectados.
- [ ] **Critico** - Existe estimacion de tiempo y su base esta explicada.
- [ ] **Critico** - Existe estimacion de costo o una justificacion explicita de por que no aplica.
- [ ] El impacto en calidad identifica riesgos, regresiones o validaciones necesarias.
- [ ] El riesgo principal del cambio esta declarado.

### 2.3 Trazabilidad y pruebas

- [ ] **Critico** - El `CR` referencia el `REQ` afectado o declara que se generara uno si el cambio es aprobado.
- [ ] Se listan casos de prueba nuevos, actualizados o la razon por la que no aplican.
- [ ] La matriz de trazabilidad aparece como artefacto a actualizar cuando corresponde.

### 2.4 Validacion y decision

- [ ] **Critico** - El cambio no se presenta como aprobado sin evidencia escrita del cliente.
- [ ] La decision del cliente esta registrada con fecha y nombre del aprobador.
- [ ] Si el cambio fue rechazado o ajustado, la causa esta documentada.

### 2.5 Cierre del expediente

- [ ] El responsable de implementacion y la fecha compromiso estan definidos cuando el cambio fue aprobado.
- [ ] El estado final del `CR` coincide con la evidencia de implementacion o rechazo.
- [ ] `REQ`, pruebas y trazabilidad fueron actualizados o se documenta por que no aplica.
- [ ] El historial de cambios del `CR` esta actualizado.

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
| H-01 | [Defecto identificado] | [Alta / Media / Baja] | [Correcion requerida] | [Nombre] | [YYYY-MM-DD] |

## 5. Cierre

- Firma o confirmacion del evaluador: ____________________
- Firma o confirmacion del autor del CR: ____________________
- Fecha de cierre: ____________________
