# Proceso de Pruebas — XookTech

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 04 |
| Proceso | Pruebas de software |
| Estándar de referencia | ISO/IEC 12207 - Verificación y Validación |
| Versión | 1.0 |
| Fecha | 2026-05-24 |
| Responsable del proceso | Analista de Verificación y Pruebas |

---

## 2. Propósito
> Derivado de ISO/IEC 12207.
> Este proceso tiene como propósito comprobar que los requisitos y cambios del Visualizador de Marcos funcionen antes de mostrarlos al Cliente, dejando evidencia mínima de qué se probó, qué resultado se obtuvo y qué ajustes quedaron pendientes.

## 3. Alcance
*   **Qué cubre:** La planeación ligera de pruebas, creación de casos de prueba, ejecución local de pruebas, registro de resultados, evidencia mínima y registro de fallos o ajustes encontrados.
*   **Qué NO cubre:** Automatización completa de pruebas, pruebas de carga, control formal de cambios, despliegue a producción ni validación comercial del Cliente.

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Verificación y Pruebas | Define casos de prueba, ejecuta pruebas y registra resultados. |
| Líder de Desarrollo e Implementación | Implementa cambios y realiza una revisión local rápida antes de pasar a pruebas. |
| Analista de Control y Cambios | Apoya cuando una prueba genera defecto, ajuste o cambio fuera del alcance inicial. |
| Cliente | Revisa avances y da visto bueno funcional cuando aplica. No ejecuta pruebas internas. |

## 5. Entradas
| Entrada                       | Origen                   | Formato actual                   |
| ----------------------------- | ------------------------ | -------------------------------- |
| Requisitos iniciales          | Reunión inicial informal | Acuerdos conversados             |
| Cambios o ajustes solicitados | Cliente                  | WhatsApp o conversación informal |
| Código modificado             | Proceso de Codificación  | Cambios locales en el sistema    |
| Casos de prueba existentes    | Plan SQA                 | Markdown en Obsidian             |

## 6. Salidas (Artefactos)
| Artefacto                        | Destino                        | Formato actual                 |
| -------------------------------- | ------------------------------ | ------------------------------ |
| Plan de pruebas ligero           | Carpeta de pruebas             | Markdown en Obsidian           |
| Caso de prueba                   | Carpeta de pruebas             | Markdown en Obsidian           |
| Registro de ejecución de pruebas | Aseguramiento de Calidad       | Markdown en Obsidian           |
| Defecto o ajuste detectado       | Registro de defectos / control | Markdown o nota de seguimiento |
| Evidencia de prueba              | Caso o registro de ejecución   | Captura, log o nota breve      |

## 7. Pasos del Proceso
Cómo se hacía originalmente en la empresa

1.  **Recepción informal de requisitos:** El proyecto inició con una reunión informal. Después, los avances y cambios se manejaban principalmente por WhatsApp.
2.  **Implementación directa del cambio:** El Líder de Desarrollo e Implementación modificaba el código con base en lo que solicitaba el Cliente.
3.  **Revisión visual inicial:** El desarrollador revisaba “a ojo” si el cambio funcionaba en la aplicación local.
4.  **Muestra al Cliente:** Si el cambio parecía funcionar, se mostraba al Cliente por WhatsApp o demostración informal.
5.  **Ajustes posteriores:** Si el Cliente pedía ajustes, se corregía el código sin un caso de prueba formal.
6.  **Cierre informal:** No se registraba de forma estándar qué se probó, qué falló o qué quedó aprobado.

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| WhatsApp | Recepción de solicitudes, envío de avances y visto bueno del Cliente. |
| Navegador / ejecución local | Revisión manual del funcionamiento del sistema. |
| Obsidian / Markdown | Documentación propuesta de pruebas, casos y resultados. |
| Capturas o logs | Evidencia mínima de ejecución. |

## 9. Problemas y Hallazgos Identificados
Esta sección resume las brechas del proceso original frente a prácticas básicas de calidad.

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | No existía un plan de pruebas antes del Plan SQA. | ISO 12207 - Verificación |
| **H-02** | Los cambios se revisaban “a ojo” por el mismo rol que los implementaba. | CMMI-DEV v2.0 - Verificación |
| **H-03** | No existían casos de prueba formales ni repetibles. | ISO 12207 - Validación |
| **H-04** | No se guardaba evidencia estándar de ejecución. | CMMI-DEV v2.0 - PPQA |
| **H-05** | Los defectos o ajustes se comunicaban informalmente por WhatsApp. | CMMI-DEV v2.0 - Seguimiento del trabajo |
| **H-06** | Los cambios fuera del alcance inicial no siempre generaban pruebas específicas. | CMMI-DEV v2.0 - Planeación y control |

## 10. Métricas Actuales
*   **Estado de las métricas:** El proceso original de pruebas no cuenta con métricas formales.
*   **Diagnóstico:** No se mide cuántos requisitos tienen caso de prueba, cuántos cambios fueron probados, cuántos fallos se detectaron ni qué avances fueron aprobados por el Cliente con evidencia.
