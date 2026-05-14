---
id: IDX-01
titulo: Indice de Procesos - Sistema de Gestion de Calidad
version: "1.0"
estado: Activo
tipo: Indice
fecha_creacion: 2026-03-19
ultima_revision: 2026-04-14
responsable: Samuel Blanco
referencias_biblio:
  - "SWEBOK v4 KA8"
  - "O'Regan - A Practical Approach to Software Quality"
tags:
  - meta/indice
  - proceso
---

# Indice de Procesos - Sistema de Gestion de Calidad

> Punto de entrada principal al SGC del proyecto Visualizador de Marcos.

---

## 1. Arquitectura del SGC (Ciclo de Vida Adaptado)

```
+----------------------------------------------------------+
|              METAPROCESO 0: GOBERNANZA DEL VAULT         |
|  (Estructura, convenciones, tags y plantillas)             |
+----------------------------------------------------------+
        |               |               |              |
        v               v               v              v
  PROCESO 1       PROCESO 2       PROCESO 3       PROCESO 4
  Linea Base      Requisitos      Diseño del      Codificacion
  (Contexto)      (REQ)           Sistema         (Implementacion)
        |               |               |              |
        +-------+-------+-------+-------+              |
                |                |                      |
                v                v                      v
          PROCESO 5: PRUEBAS (V&V)         PROCESO 6: MANTENIMIENTO
                |                                      |
                +-----------------+--------------------+
                                  v
                        PROCESO 7: CONTROL 
                (Cambios, Inspecciones, Metricas, SCM)
```

---

## 2. Descripcion de Procesos

| ID | Proceso | Objetivo | Responsable | Estado |
| :-- | :-- | :-- | :-- | :-- |
| PROC-00 | Gobernanza Vault | Estándares y convenciones | Axel Morales | Activo |
| PROC-01 | Linea Base | Contexto y acuerdos iniciales | Axel Morales | Completado |
| PROC-02 | Requisitos | Especificacion profunda (REQ) | Carlos Yonson | En_Progreso |
| PROC-03 | Diseño | Arquitectura y componentes (DIS) | Axel Morales | Pendiente |
| PROC-04 | Codificacion | Implementación técnica (COD) | Samuel Blanco | Pendiente |
| PROC-05 | Pruebas | Verificación y Validación (CP) | Axel Morales | En_Progreso |
| PROC-06 | Mantenimiento | Soporte y mejora (MNT) | Samuel Blanco | Pendiente |
| PROC-07 | Control | SCM, Cambios e Inspecciones (CTRL) | Carlos Yonson | En_Progreso |
| PROC-08 | Despliegue | Puesta en producción y entrega (DESP) | Samuel Blanco | Pendiente |

---

## 3. Flujo de Procesos

```
PROC-01 (Linea Base)
       |
       v
PROC-02 (Req. Profundos) ----> PROC-03 (Control de Cambios)
       |                              |
       +------------+------------------+
                    v
PROC-04 (Arquitectura)
       |
       v
PROC-05 (Pruebas)
       |
       v
PROC-06 (Inspecciones)
```

---

## 4. Matriz de Trazabilidad

| REQ | PROC-01 | PROC-02 | PROC-03 | PROC-04 | PROC-05 | PROC-06 |
| :-- | :--: | :--: | :--: | :--: | :--: | :--: |
| REQ-01 | - | Crea | - | - | Prueba | Revisa |
| REQ-02 | - | Crea | - | - | Prueba | Revisa |
| REQ-03 | - | Crea | - | Doc | Prueba | Revisa |
| REQ-04 | - | Crea | - | - | Prueba | Revisa |
| REQ-05 | - | Crea | - | - | Prueba | Revisa |
| REQ-06 | - | Crea | - | - | Prueba | Revisa |
| REQ-07 | - | Crea | CR-01 | - | Prueba | Revisa |
| REQ-08 | - | Crea | CR-02 | - | Prueba | Revisa |
| REQ-09 | - | Crea | CR-03 | - | Prueba | Revisa |
| REQ-10 | - | Crea | CR-04 | - | Prueba | Revisa |

---

## 5. Referencias

### Meta
- [[00-PROC-00_Gobernanza_Vault]]
- [[01-Plan_Accion]]
- [[02-Estandar_Estructura_Procesos]]
- [[03-Convenciones_y_Tags]]
- [[04-Glosario]]

### Procesos
- [[01-PROC-01_Recuperacion_Linea_Base]]
- [[02-Requerimientos/PROC-02_Especificacion_Requerimientos]]
- [[07-Control/PROC-03_Control_Cambios]]
- [[04-Arquitectura/PROC-04_Arquitectura_Sistema]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/05-Pruebas/PROC-05_Plan_Pruebas]]
- [[06-Inspecciones/PROC-06_Inspecciones]]

### Metricas
- [[07-Metricas/00-Dashboard_Calidad]]
- [[07-Metricas/01-Registro_Defectos]]

---

*Indice creado: 2026-03-19*
