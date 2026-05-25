# Proceso de Diseño de Software — XookTech

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Requisitos de software aprobados en la fase de ingeniería de requerimientos, restricciones tecnológicas del proyecto y lineamientos de arquitectura de la organización.  
**Salidas:** Diagnóstico del estado actual (As-Is) del proceso de diseño, catálogo de brechas arquitectónicas y hallazgos contra ISO/IEC 12207 §6.4.4 e IEEE Std 1016.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 03 |
| Proceso | Diseño de la Arquitectura y Componentes de Software |
| Estándar de referencia | ISO/IEC 12207 §6.4.4 (Proceso de Diseño de la Arquitectura del Software) / IEEE Std 1016-2009 |
| Versión | 1.0 |
| Fecha | 2026-05-25 |
| Responsable del proceso | Analista de Gobernanza y Diseño |

---

## 2. Propósito
> Derivado de ISO/IEC 12207 §6.4.4.
> Este proceso tiene como propósito producir una descripción de diseño de software verificable que transforme los requisitos aprobados en una arquitectura modular, detallando la descomposición lógica y física del sistema en componentes con interfaces definidas, modelos de datos y flujos de comportamiento que guíen  la fase de codificación.

## 3. Alcance
*   **Qué cubre:** La definición de la arquitectura lógica y física del sistema, la descomposición en componentes y subsistemas, el modelado de interfaces de programación (APIs y rutas), el diseño del modelo de datos y persistencia, la diagramación del flujo de comportamiento del sistema y la verificación de consistencia del diseño frente a los requisitos aprobados.
*   **Qué NO cubre:** La captura y especificación de requisitos de usuario, la escritura del código fuente, la ejecución de pruebas unitarias o de integración, ni el despliegue a entornos de producción.

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Gobernanza y Diseño | Define la arquitectura lógica y física del sistema, produce los diagramas técnicos en Mermaid.js, redacta el Documento de Descripción de Diseño (SDD) y valida la trazabilidad del diseño con los requisitos. |
| Líder de Desarrollo e Implementación | Valida la viabilidad técnica de la arquitectura propuesta frente a las restricciones tecnológicas del entorno de producción (Flask, OpenCV, VPS). |
| Revisor SQA | Ejecuta el checklist de verificación de diseño sobre el SDD antes de autorizar la transición a codificación. |

## 5. Entradas
| Entrada | Origen | Formato actual |
|---|---|---|
| Requisitos del sistema | Proceso de Requisitos (02) | Inexistente — requisitos verbales o en chats informales |
| Restricciones tecnológicas | Líder de Desarrollo | Conocimiento tácito no documentado |
| Lineamientos de arquitectura | Biblioteca de Procesos | Inexistente — no se cuenta con un estándar de diseño formalizado |

## 6. Salidas (Artefactos)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Documento de Descripción de Diseño (SDD) | Equipo de Desarrollo | Inexistente — no se produce un SDD formal |
| Diagramas de Arquitectura | SGC del Proyecto | Inexistente — se codifica directamente sin diagramas previos |
| Modelo de Datos | Equipo de Desarrollo / DBA | Inexistente — el esquema se define improvisadamente en tiempo de codificación |

## 7. Pasos del Proceso
Cómo se hace hoy en la empresa

1.  **Ausencia total de fase de diseño:** El equipo de XookTech no cuenta con una fase formal de diseño de software. La transición de requisitos a codificación se realiza de forma directa, sin producir ningún artefacto de arquitectura intermedio.
2.  **Codificación directa sin arquitectura:** Los programadores inician la escritura de código basándose exclusivamente en instrucciones verbales del líder del proyecto, sin contar con diagramas de componentes, flujos de sistema ni modelo de datos documentado.
3.  **Decisiones tecnológicas implícitas:** Las decisiones de tecnología (lenguaje, framework, base de datos) se toman de manera improvisada y no quedan registradas en ningún documento de justificación técnica.
4.  **Modelo de datos ad-hoc:** Las tablas de base de datos, esquemas JSON y estructuras de persistencia se definen sobre la marcha durante la codificación, sin un diseño previo que garantice la integridad referencial y la normalización.
5.  **Ausencia de interfaces formales:** Las firmas de funciones, rutas de API y contratos de comunicación entre componentes no se especifican antes de codificar, provocando acoplamientos fuertes e interfaces rotas entre subsistemas.

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| N/A | No se utilizan herramientas de modelado de diseño, ya que el proceso es inexistente |

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

## 10. Métricas Actuales
*   **Estado de las métricas:** El proceso de diseño de software de XookTech no cuenta actualmente con ninguna métrica definida, ya que el proceso mismo es inexistente.
*   **Diagnóstico:** La ausencia total de un proceso de diseño imposibilita la medición de la densidad de defectos de arquitectura, la cobertura de requisitos en el diseño y la alineación de interfaces, bloqueando cualquier iniciativa de mejora continua cuantificable (CMMI-DEV Nivel 2).
