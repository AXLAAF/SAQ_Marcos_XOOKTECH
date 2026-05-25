# Proceso de Diseño de Software — XookTech

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Requisitos aprobados.  
**Salidas:** Diagnóstico del proceso actual, análisis de brechas y listado de diseño.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 03 |
| Proceso | Diseño de la Arquitectura y Componentes de Software |
| Estándar de referencia | ISO/IEC 12207:2017 §6.4.4 (Proceso de diseño de arquitectura de software) |
| Versión | 1.0 |
| Fecha | 2026-05-25 |
| Responsable del proceso | Analista de Gobernanza y Diseño |

---

## 2. Propósito
> Derivado de ISO/IEC 12207.
> Este proceso tiene como propósito producir una descripción de diseño de software verificable que transforme los requisitos aprobados en una arquitectura modular, detallando la descomposición lógica y física del sistema en componentes con interfaces definidas, modelos de datos y flujos de comportamiento que guíen la fase de codificación.

## 3. Alcance
* **Qué cubre:** Definición de la arquitectura lógica y física del sistema, descomposición en componentes, modelado de interfaces (APIs y rutas), diseño del modelo de datos, diagramación de flujos de comportamiento y verificación de la consistencia del diseño.
* **Qué NO cubre:** Elicitación y especificación de requisitos (Fase 02), escritura del código fuente (Fase 06), pruebas unitarias o de integración (Fase 04), ni el despliegue final a producción (Fase 07).

---

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Gobernanza y Diseño | Define la arquitectura lógica y física, genera diagramas en Mermaid.js, redacta el Documento de Descripción de Diseño (SDD) y valida la trazabilidad con los requisitos. |
| Líder de Desarrollo e Implementación | Valida la viabilidad técnica de la arquitectura propuesta frente a las restricciones del entorno. |
| Revisor SQA | Ejecuta el checklist de calidad sobre el SDD antes de autorizar la transición a codificación. |

---

## 5. Entradas
| Entrada | Origen | Formato actual |
|---|---|---|
| Requisitos del sistema | Proceso de Requisitos (02) | Notas sueltas, vagas o verbales sin estructura formal. |
| Restricciones tecnológicas | Líder de Desarrollo | Conocimiento tácito del equipo sin documentación formal. |
| Lineamientos de arquitectura | Biblioteca de Procesos | Inexistente. No se cuenta con un estándar de diseño de software actual. |

---

## 6. Salidas (Artefactos)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Documento de Descripción de Diseño (SDD) | Equipo de Desarrollo | Inexistente. No se produce ningún documento de arquitectura formal. |
| Diagramas de Arquitectura | SGC del Proyecto | Inexistente. Se inicia la programación directamente sin modelado visual previo. |
| Modelo de Datos | Equipo de Desarrollo / BD | Inexistente de forma previa. El esquema de datos se crea al vuelo durante la codificación. |

---

## 7. Pasos del Proceso
How it is done today in the company

1. **Sin fase de diseño:** XookTech no cuenta con una fase de diseño de software formal. Se pasa directamente de los requisitos a escribir código.
2. **Codificación directa:** Los desarrolladores escriben código fuente basándose en instrucciones puramente verbales, sin contar con diagramas de componentes o de flujo de datos.
3. **Decisiones implícitas:** Las elecciones tecnológicas se realizan de forma improvisada sobre la marcha, sin registrar su justificación técnica en bitácoras.
4. **Modelo de datos ad-hoc:** Las tablas de bases de datos y esquemas de persistencia se definen directamente en la codificación, sin diseño de integridad relacional previo.
5. **Sin interfaces especificadas:** Las firmas de funciones y rutas de API no se definen antes de codificar, provocando problemas de integración entre componentes.

---

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| N/A | No se utilizan herramientas de modelado de arquitectura actualmente debido a la inexistencia del proceso. |

---

## 9. Problemas y Hallazgos Identificados
Esta sección es el núcleo del diagnóstico. Identifica las brechas contra estándares reconocidos.

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | No existe una fase de diseño de software formalizada en el ciclo de vida del proyecto. | ISO/IEC 12207 §6.4.4 (Proceso de Diseño Arquitectónico) |
| **H-02** | No se produce un Documento de Descripción de Diseño (SDD) que guíe la codificación. | IEEE Std 1016-2009 / SWEBOK v4 Cap. 2 |
| **H-03** | Las decisiones tecnológicas y de arquitectura no se documentan ni justifican formalmente. | CMMI-DEV v2.0 TS SP 1.1 (Selección de Soluciones) |
| **H-04** | No existen diagramas de descomposición lógica, comportamiento dinámico ni vista física del sistema. | IEEE Std 1016-2009 (Viewpoints) |
| **H-05** | El modelo de datos y las interfaces de componentes se definen improvisadamente durante la codificación. | ISO/IEC 12207 §6.4.4 / SWEBOK v4 Cap. 2 |
| **H-06** | Ausencia de trazabilidad bidireccional entre requisitos aprobados y elementos de diseño. | CMMI-DEV v2.0 TS SP 2.2 / ISO/IEC 12207 |
| **H-07** | No existe un checklist de verificación de calidad de diseño previo a la transición a codificación. | CMMI-DEV v2.0 PPQA SP 1.1 / IEEE 1028-2008 |

---

## 10. Métricas Actuales
* **Estado de las métricas:** El proceso de diseño de software de XookTech no cuenta actualmente con ninguna métrica definida.
* **Diagnóstico:** La falta de un proceso formal y de métricas impide evaluar la densidad de defectos de arquitectura, la cobertura de requisitos en el diseño y la alineación de interfaces, bloqueando la mejora continua (CMMI Nivel 2).
