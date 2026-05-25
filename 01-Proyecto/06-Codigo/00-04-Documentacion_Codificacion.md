# Proceso de Codificación — XookTech

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 04 |
| Proceso | Codificación de funcionalidades del sistema |
| Estándar de referencia | ISO/IEC 12207 §6.4.1 (Proceso de Implementación de Software) |
| Versión | 1.0 |
| Fecha | 2026-05-24 |
| Responsable del proceso | Líder de Desarrollo e Implementación |

---

## 2. Propósito
> Derivado de ISO/IEC 12207.
> Este proceso tiene como propósito producir módulos de software verificados y de calidad a partir de los requisitos y elementos de diseño documentados, transformando especificaciones abstractas en código fuente reproducible, seguro, mantenible y robusto.

## 3. Alcance
*   **Qué cubre:** El desarrollo local del código fuente en lenguajes definidos (Python/Flask, JavaScript, etc.), la estructuración de la lógica de negocio, las migraciones y operaciones de base de datos relacional, la creación de vistas o páginas web, la conexión asíncrona entre cliente/servidor y la verificación local inicial mediante pruebas unitarias o de integración.
*   **Qué NO cubre:** La especificación de requerimientos de usuario, el diseño arquitectónico de alto nivel, la ejecución de las fases de pruebas del sistema completas en ambientes controlados, ni el despliegue final a producción.

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Líder de Desarrollo e Implementación | Asigna tareas formales de construcción, resguarda el estándar de codificación de la organización y valida la integración final a la rama principal. |
| Programador / Desarrollador | Revisa documentación de diseño, codifica la funcionalidad, realiza la autoverificación de calidad y solicita la revisión por pares. |
| Revisor independiente | Integrante del equipo técnico responsable de inspeccionar el código desarrollado frente a la lista de verificación formal antes de autorizar la integración. |

## 5. Entradas
| Entrada | Origen | Formato actual |
|---|---|---|
| Requerimientos de la funcionalidad | Líder del Proyecto | Comunicación verbal e informal (chats dispersos o WhatsApp) |
| Insumos de diseño / Esquema BD | Analista de Requisitos | Archivos sueltos, diagramas de base de datos incompletos o inexistentes |
| Estándar de Codificación | Biblioteca de Procesos | Inexistente (no se cuenta con un estándar de codificación actual formalizado) |

## 6. Salidas (Artefactos)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Código fuente funcional | Repositorio de control de versiones | Ramas locales o integraciones directas a producción |
| Registro de Tareas de Desarrollo | Gestión de Proyecto | Listados informales o inexistentes de avance técnico |
| Lista de Verificación | Aseguramiento de Calidad | Inexistente (se realizan revisiones manuales, informales y limitadas al flujo principal) |

## 7. Pasos del Proceso
 Cómo se hace hoy en la empresa 

1.  **Recepción informal de tareas:** El líder del proyecto le comunica al programador verbalmente o por WhatsApp qué funcionalidad debe codificar, sin que exista un folio o registro de asignación formal.
2.  **Revisión improvisada de documentación:** El programador intenta codificar consultando la escasa información de diseño y base de datos disponible. Si no hay documentos, programa con base en su libre albedrío y criterio empírico.
3.  **Configuración discrecional del repositorio:** El desarrollador inicializa el repositorio local solo si lo considera necesario y comparte los accesos de manera informal mediante redes sociales o correos del equipo.
4.  **Acoplamiento directo:** Se revisa visualmente el código circundante y se añaden nuevas rutinas sin validar formalmente el impacto arquitectónico.
5.  **Codificación aislada y commits genéricos:** Se escribe el código fuente aplicando convenciones variables. Los cambios en Git se suben mediante mensajes genéricos como `"avance"`, `"fix"` o `"cambios"`.
6.  **Autoverificación subjetiva:** El mismo desarrollador que escribió el código realiza una revisión empírica rápida para confirmar que "funciona en su máquina" y da por terminada la actividad.
7.  **Integración no regulada:** El programador une sus desarrollos directamente a la rama principal del repositorio, asumiendo de buena fe que no se introducen regresiones.

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| WhatsApp / Chats informales | Comunicación de requerimientos y tareas de programación |
| Git y GitHub | Control de versiones básico (uso intermitente e individual) |
| Editores / IDEs locales | Escritura directa del código de la aplicación |

## 9. Problemas y Hallazgos Identificados
Esta sección es el núcleo del diagnóstico. Identifica las brechas contra estándares reconocidos.

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | La comunicación de asignación de tareas es verbal y no deja evidencia. | ISO 12207 §6.4.1.3 / SWEBOK v4 Cap. 3 |
| **H-02** | Se inicia la codificación sin contar con insumos estables (requisitos o diseños documentados). | ISO 12207 §6.4.1.2 |
| **H-03** | La creación y uso de repositorios de control de versiones no es obligatorio ni estandarizado al inicio del proyecto. | SWEBOK v4 Cap. 5 (Gestión de la Configuración) |
| **H-04** | Se modifica e integra código sin analizar formalmente la coherencia arquitectónica y el impacto lateral. | SWEBOK v4 Cap. 3 (Construcción de Software) |
| **H-05** | Mensajes de confirmación de cambios (commits) vacíos o ambiguos, lo que anula la trazabilidad técnica. | ISO 12207 §6.4.1.3 |
| **H-06** | Falta de aplicación de un estándar unificado para nomenclatura, explicitación e idioma en el código fuente. | ISO/IEC 25010 / SWEBOK v4 Cap. 3 |
| **H-07** | Ausencia de un filtro de revisión por pares o de control de calidad objetivo previo a la integración final. | CMMI-DEV v2.0 PPQA SP 1.1 / IEEE 1028-2008 |

## 10. Métricas Actuales
*   **Estado de las métricas:** El proceso de codificación de XookTech no cuenta actualmente con ninguna métrica definida para medir la densidad de defectos, el tiempo de entrega de tareas, ni el cumplimiento del estándar de codificación.
*   **Diagnóstico:** La falta de métricas imposibilita la visibilidad del rendimiento y bloquea cualquier iniciativa de mejora continua cuantificable (CMMI-DEV Nivel 2).
