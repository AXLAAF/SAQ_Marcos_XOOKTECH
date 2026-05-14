---
id: CONT-01
titulo: Contrato de Desarrollo de Software - Simulador 3D Enmarcame
version: "1.0"
estado: Vigente
tipo: Contrato
fecha_creacion: 2026-04-14
responsable: Líder SQA
cliente: Cliente
desarrollador: Líder SQA
referencias:
  - PROC-01_Recuperacion_Linea_Base
  - 01-Propuesta_Recuperada
  - 02-Acuerdos_Cliente
tags:
  - contrato
  - baseline
  - legal
---

# Contrato de Desarrollo de Software — Simulador 3D Enmarcame

> Contrato de prestacion de servicios de desarrollo de software SIMULADOR 3D ENMARCAME. Este documento formaliza el alcance, condiciones y compromisos entre ambas partes. Su existencia reemplaza la suposicion previa de que no habia contrato formal.

Artefacto de salida de [[01-Baseline/00-PROC-01_Recuperacion_Linea_Base]]. Este contrato es la referencia legal principal del proyecto. Su contenido tiene precedencia sobre los acuerdos verbales documentados en [[01-Baseline/03-Acuerdos_Cliente]] y actualiza el alcance documentado en [[01-Baseline/02-Propuesta_Recuperada]].

---

## Partes del Contrato

| Parte | Nombre | Rol |
|-------|--------|-----|
| **EL CLIENTE** | Cliente | Dueño de Enmarcame |
| **EL DESARROLLADOR** | Líder SQA | Lider tecnico |

---

## PRIMERA. Objeto del Contrato

EL DESARROLLADOR se compromete a desarrollar y mejorar **dos MODULOS DEL MISMO SISTEMA SIMULADOR 3D ENMARCAME** de visualizacion virtual de enmarcado con las siguientes funciones:

| # | Funcionalidad Contractual | REQ Asociado |
|---|--------------------------|--------------|
| 1 | Visualizacion de doble marco con separacion maxima de 2 mm | REQ-07 (Marcos Dobles) |
| 2 | Control de reflejos en molduras con distintos niveles de iluminacion en la habitacion | REQ-11 (Nuevo) |
| 3 | Mejora visual de molduras y sombras conforme a referencia enviada por WhatsApp el jueves 26 a las 8:07 pm | REQ-12 (Nuevo) |
| 4 | Modelado de camisas a enmarcar mediante seleccion de puntos y ajuste con IA | REQ-13 (Nuevo) |
| 5 | Generacion de enlaces para que clientes puedan visualizar sus obras virtualmente | REQ-14 (Nuevo) |
| 6 | Visualizacion de varios cuadros simultaneamente para comparacion y acomodo | REQ-15 (Nuevo) |
| 7 | Simulacion de colocacion en pared | REQ-16 (Nuevo) |
| 8 | Herramienta de medicion proporcional dentro del entorno virtual | REQ-17 (Nuevo) |
| 9 | Visualizacion en entorno 3D con lentes de realidad virtual | REQ-18 (Nuevo — ver SEPTIMA) |

> **Impacto en el SGC:** Las funcionalidades 1 ya estaba registrada como CR-01 / REQ-07 (scope creep). Con la existencia del contrato, **ya no es scope creep sino obligacion contractual**. Las funcionalidades 2-8 son requerimientos nuevos que no estaban en el REQ list original (REQ-01 a REQ-10). La funcionalidad 9 tiene clausula separada (SEPTIMA) con costo adicional.

---

## SEGUNDA. Condicion Tecnica

El proyecto **no se considerara terminado** hasta resolver el problema actual de reflejos existente en el SISTEMA BASE, y de los puntos que se mencionan en este contrato.

> **Impacto:** Define un criterio de aceptacion bloqueante: el bug de reflejos debe resolverse antes de cerrar el proyecto.

---

## TERCERA. Exclusividad

- Exclusividad de uso comercial del Programa SIMULADOR 3D ENMARCAME a EL CLIENTE dentro del sector de enmarcado.
- Periodo: **6 meses** a partir de la entrega funcional del sistema.
- Durante ese periodo el sistema no podra venderse a terceros.

---

## CUARTA. Opcion de Compra del Software

EL CLIENTE podra adquirir la propiedad total del software en cualquier momento dentro del periodo de exclusividad mediante el pago de:

| Concepto | Monto |
|----------|-------|
| Compra total del software | **$60,000 MXN** |

En ese caso EL DESARROLLADOR entregara: codigo fuente, archivos del proyecto, componentes necesarios para su funcionamiento.

---

## QUINTA. Licencia de Uso (Renta Mensual)

Mientras no se ejerza la opcion de compra:

| Concepto | Monto |
|----------|-------|
| Renta mensual del software | **$2,000 MXN** |
| Servidor mensual | **$500 MXN** |
| Sucursal extra | Costo extra adicional |
| **Total mensual (1 sucursal)** | **$2,500 MXN** |

> **Impacto:** El monto total ($2,500) coincide con lo documentado en ACU-004, pero el desglose es diferente: $2,000 renta + $500 servidor, no una tarifa plana de $2,500.

---

## SEXTA. Componentes de Hardware

Por cuenta del cliente se adquiriran componentes de computo complementarios para el desarrollo del proyecto. Dichos componentes permanecerán en propiedad del desarrollador a modo de donación.

**El visor de realidad virtual permanecera en propiedad de EL CLIENTE.**

### Anexo 1: Componentes de Hardware

| Componente | Descripcion |
|------------|-------------|
| Fuente de Alimentacion | XPG Pylon 650W, Certificacion 80 Plus Bronze (PYLON650B-BKCUS) |
| Tarjeta Grafica | ASUS Dual GeForce RTX 5060 8GB GDDR7 OC Edition (DUAL-RTX5060-O8G) |
| Tarjeta Madre | ASUS Prime B550M-A AC, AM4 mATX, PCIe 4.0, Dual M.2, WiFi |
| Procesador | AMD Ryzen 7 5700G, 8 nucleos, Socket AM4, 3.80GHz, 16MB L3 Cache |

> **Impacto:** Estos componentes son para desarrollo (generacion de modelos 3D, IA, VR). El costo lo cubre el cliente pero la propiedad es del desarrollador.

---

## SEPTIMA. Modulo de Realidad Virtual

Se desarrollara un MODULO para dispositivos de realidad virtual, especificamente probado para el **Meta Quest 3s**.

| Concepto | Monto |
|----------|-------|
| Desarrollo modulo VR | **$6,000 MXN** (en caso de conclusion del proyecto) |

---

## OCTAVA. Entrega del Proyecto

El proyecto se considerara terminado **unicamente cuando ambas partes confirmen que las funciones descritas en este contrato estan operando correctamente**.

Hasta ese momento no existira obligacion de pago final adicional distinta a lo previamente acordado.

---

## NOVENA. Propiedad del Software

En caso de no ejercerse la opcion de compra, la propiedad intelectual del software permanecera en favor de EL DESARROLLADOR.

---

## DECIMA. Vigencia

Este contrato entra en vigor a partir de su firma y permanecera vigente hasta la conclusion del proyecto o la compra del software SIMULADOR 3D ENMARCAME por parte del cliente.

---

## Firmas

| Parte | Nombre | Firma | Fecha |
|-------|--------|-------|-------|
| EL CLIENTE | Cliente | _____________ | _______ |
| EL DESARROLLADOR | Líder SQA | _____________ | _______ |

---

## Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-04-14 | Analista Técnico | Documento digitalizado e integrado al SGC como artefacto de PROC-01 |

---

*Documento integrado al SGC: 2026-04-14*
*Referencia: [[01-Baseline/00-PROC-01_Recuperacion_Linea_Base]], [[01-Baseline/02-Propuesta_Recuperada]], [[01-Baseline/03-Acuerdos_Cliente]]*
