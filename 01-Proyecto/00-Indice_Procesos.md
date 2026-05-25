# Indice de Procesos - Sistema de Gestion de Calidad

> Punto de entrada principal al SGC del proyecto Visualizador de Marcos.

---

## 1. Arquitectura del SGC (Ciclo de Vida Estandarizado de 8 Fases)

```
+------------------------------------------------------------+
|             FASE 01: GESTIÓN DE LA CONFIGURACIÓN           |
| (PROC-01: Gobernanza, SCM, estándares, tags y plantillas) |
+------------------------------------------------------------+
        |               |               |               |
        v               v               v               v
    FASE 02         FASE 03         FASE 04         FASE 05
   Requisitos       Diseño        Codificación      Control
    (PROC-02)      (PROC-03)       (PROC-04)        (PROC-05)
        |               |               |               |
        v               v               v               v
    FASE 06         FASE 07         FASE 08         MEJORA
    Pruebas       Despliegue     Mantenimiento    CONTINUA
    (PROC-06)      (PROC-07)       (PROC-08)       (PDCA)
```

---

## 2. Descripción de Procesos

| ID | Área de Proceso | Objetivo de Aseguramiento SQA | Responsable Técnico | Estado |
| :--- | :--- | :--- | :--- | :--- |
| **PROC-01** | Gestión de la Configuración | Estándares de calidad, taxonomía y SCM global | Analista de Gobernanza y Diseño | Activo |
| **PROC-02** | Requisitos | Especificación profunda con escenarios BDD | Analista de Requerimientos | Activo |
| **PROC-03** | Diseño | Arquitectura, modelo de datos y Mermaid | Analista de Gobernanza y Diseño | Activo |
| **PROC-04** | Codificación | Construcción verificada en Python/Flask | Líder de Desarrollo | Activo |
| **PROC-05** | Control de Cambios | SCM, solicitudes de cambio e inspecciones SQA | Analista de Control y Cambios | Activo |
| **PROC-06** | Pruebas | Casos de prueba exhaustivos y bitácoras SQA | Analista de Verificación y Pruebas | Activo |
| **PROC-07** | Despliegue | Paquete de entrega y Guía de Instalación | Líder de Desarrollo | Activo |
| **PROC-08** | Mantenimiento | Soporte post-despliegue y control de incidentes | Analista de Control y Cambios | Activo |

---

## 3. Flujo y Causalidad de Procesos

```
PROC-01 (Gobernanza y SCM)
       |
       v
PROC-02 (Requisitos BDD) ======> PROC-03 (Diseño de Componentes)
       |                                     |
       +------------------+------------------+
                          v
                    PROC-04 (Codificación Flask)
                          |
                          v
                    PROC-05 (Control de Cambios e Inspecciones)
                          |
                          v
                    PROC-06 (Pruebas SQA y Bitácoras)
                          |
                          v
                    PROC-07 (Despliegue y Empaquetado)
                          |
                          v
                    PROC-08 (Mantenimiento de Software)
```

---

## 4. Matriz de Trazabilidad General

| Requisito | PROC-02 | PROC-03 | PROC-04 | PROC-05 | PROC-06 | PROC-08 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **REQ-01** (Carga) | Crea | STD-04 | COD-01 | CR-01 | CP-01 | MNT-01 |
| **REQ-02** (Previsualizar) | Crea | STD-05 | COD-02 | - | CP-08 | MNT-01 |
| **REQ-03** (3D) | Crea | STD-06 | COD-03 | - | CP-08 | MNT-01 |
| **REQ-04** (Catálogo) | Crea | STD-07 | COD-04 | - | CP-04 | MNT-01 |
| **REQ-05** (Filtrar) | Crea | STD-07 | COD-04 | - | CP-05 | MNT-01 |
| **REQ-06** (Datos) | Crea | STD-06 | COD-03 | - | CP-04 | MNT-01 |
| **REQ-07** (Dobles) | Crea | STD-04 | COD-01 | CR-01 | CP-09 | MNT-01 |
| **REQ-08** (Vidrio) | Crea | TBD | TBD | CR-02 | CP-10 | MNT-01 |
| **REQ-09** (María Luisa) | Crea | TBD | TBD | CR-03 | CP-11 | MNT-01 |
| **REQ-10** (Secundaria) | Crea | TBD | TBD | CR-04 | CP-13 | MNT-01 |

---

## 5. Referencias

### Meta
- [[01-PROC-01_Gobernanza_Vault]]
- [[01-Gestion de la configuracion/01-PLAN-01_Accion_SQA|PLAN-01 Plan de Acción SQA]]
- [[01-Gestion de la configuracion/02-STD-01_Estandar_ETVX|STD-01 Estándar ETVX]]
- [[01-Gestion de la configuracion/03-STD-02_Convenciones_Tags|STD-02 Convenciones y Tags]]
- [[01-Gestion de la configuracion/04-GLO-01_Glosario_Terminos|GLO-01 Glosario]]

### Procesos
- [[09-Notes/01-Linea_Base-Original/00-PROC-01_Recuperacion_Linea_Base|PROC-01 Recuperación de Línea Base]]
- [[02-Requisitos/02-PROC-02_Especificacion_Requerimientos|PROC-02 Especificación de Requerimientos]]
- [[03-Diseño/03-PROC-03_Diseño_Sistema|PROC-03 Diseño de Sistema]]
- [[06-Codigo/00-04-Documentacion_Codificacion|PROC-04 Codificación - Documentación]]
- [[06-Codigo/00-04-Plan_De_Mejora_Codificacion|PROC-04 Codificación - Plan de Mejora]]
- [[05-Revisiones e inspecciones/05-PROC-05.1_Control_Cambios|PROC-05 Control de Cambios]]
- [[04-Pruebas/06-PROC-06_Plan_Pruebas|PROC-06 Plan de Pruebas]]
- [[07-Despliegue/00-07-Documentacion_Despliegue|PROC-07 Despliegue - Documentación]]
- [[07-Despliegue/00-07-Plan_De_Mejora_Despliegue|PROC-07 Despliegue - Plan de Mejora]]
- [[08-Mantenimiento/00-08-Documentacion_Mantenimiento|PROC-08 Mantenimiento - Documentación]]
- [[08-Mantenimiento/00-08-Plan_De_Mejora_Mantenimiento|PROC-08 Mantenimiento - Plan de Mejora]]
- [[05-Revisiones e inspecciones/05-PROC-05.2_Inspecciones|PROC-09 Inspecciones]]

### Metricas y Gobernanza
- [[05-Revisiones e inspecciones/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08 Dashboard de Calidad]]
- [[05-Revisiones e inspecciones/02-Calidad_Control/PLT-STD_Tablero_Calidad|STD-08-PLT Plantilla de Tablero de Calidad]]
- [[05-Revisiones e inspecciones/02-Calidad_Control/02-REG-03_Registro_Defectos|REG-03 Registro de Defectos]]
- [[07-Despliegue/Plantillas/Formatos/PLT-FOR_Plan_Smoke_Tests|PLT-FOR Plan de Smoke Tests]]
- [[07-Despliegue/Plantillas/Formatos/PLT-FOR_Configuracion_Entorno|PLT-FOR Configuración de Entorno]]

---

*Indice actualizado: 2026-05-25*

