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
| PROC-00 | Gobernanza Vault | Estándares y convenciones | Analista Técnico | Activo |
| PROC-01 | Linea Base | Contexto y acuerdos iniciales | Analista Técnico | Completado |
| PROC-02 | Requisitos | Especificacion profunda (REQ) | Analista SQA | En_Progreso |
| PROC-03 | Diseño | Arquitectura y componentes (DIS) | Analista Técnico | Pendiente |
| PROC-04 | Codificacion | Implementación técnica (COD) | Líder SQA | Pendiente |
| PROC-05 | Pruebas | Verificación y Validación (CP) | Analista Técnico | En_Progreso |
| PROC-06 | Mantenimiento | Soporte y mejora (MNT) | Líder SQA | Pendiente |
| PROC-07 | Control | SCM, Cambios e Inspecciones (CTRL) | Analista SQA | En_Progreso |
| PROC-08 | Despliegue | Puesta en producción y entrega (DESP) | Líder SQA | Pendiente |

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
- [[00-Meta/01-PLAN-01_Accion_SQA|PLAN-01 Plan de Acción SQA]]
- [[00-Meta/02-STD-01_Estandar_ETVX|STD-01 Estándar ETVX]]
- [[00-Meta/03-STD-02_Convenciones_Tags|STD-02 Convenciones y Tags]]
- [[00-Meta/04-GLO-01_Glosario_Terminos|GLO-01 Glosario]]

### Procesos
- [[01-Linea_Base/00-PROC-01_Recuperacion_Linea_Base|PROC-01 Recuperación de Línea Base]]
- [[02-Requisitos/00-PROC-02_Especificacion_Requerimientos|PROC-02 Especificación de Requerimientos]]
- [[07-Control/03-PROC-08_Control_Cambios|PROC-08 Control de Cambios]]
- [[03-Diseño/00-PROC-03_Diseño_Sistema|PROC-03 Diseño de Sistema]]
- [[00-PROC-05_Plan_Pruebas]]
- [[07-Control/04-PROC-09_Inspecciones|PROC-09 Inspecciones]]

### Metricas
- [[07-Control/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08 Dashboard de Calidad]]
- [[07-Control/02-Calidad_Control/02-REG-03_Registro_Defectos|REG-03 Registro de Defectos]]

---

*Indice creado: 2026-03-19*
