---
id: PROC-02
titulo: Proceso 2 - Especificacion de Requerimientos
version: "2.0"
estado: Activo
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-13
responsable: Samuel Blanco (Lider) / Axel Morales (Desarrollador)
disparador: Solicitud de cambio o nueva funcionalidad por parte del cliente
criterio_entrada: Solicitud documentada en acta, correo o minuta de entrevista
criterio_salida: Nota de requerimiento en estado "Aprobado" en carpeta 01-Aprobados
entradas:
  - 01-Propuesta_Recuperada.md
  - 02-Acuerdos_Cliente.md
  - 04-Minuta_Entrevista.md
salidas:
  - REQ-XXX.md (especificacion detallada)
  - Evidencia de aprobacion (.png)
  - Matriz de trazabilidad actualizada
notacion: "NT: indica una Nota Técnica con sugerencia de mejora al proceso."
---

# Proceso 2 — Especificación de Requerimientos (SQA-Obsidian)

> **Fundamentación**: Este proceso sigue los lineamientos de CMMI-DEV (REQM) y ISO 9001, utilizando el modelo **ETVX** y la infraestructura de **Galin** para asegurar que cada requerimiento sea medible, rastreable y aprobado formalmente.

## 1. Estructura del Proceso (ETVX)

| Fase | Definición | Detalles |
| :--- | :--- | :--- |
| **[E] Entry** | Criterios de Entrada | Solicitud capturada en [[04-Minuta_Entrevista]] o canal oficial. |
| **[T] Tasks** | Tareas Operativas | Fases 1 a 4: Captura, Revisión, Validación y Línea Base. |
| **[V] Verification** | Verificación de Calidad | Aplicación de [[CL-02_Verificacion_Requerimientos]] + Revision Samuel/Axel. |
| **[X] Exit** | Criterios de Salida | Archivo movido a `01-Aprobados` con estado "Aprobado". |

## 2. Proceso Detallado (Actualmente vs Propuesta)

### Paso 1: Captura de Requisitos (Planear)

**Actualmente:**
- El cliente (Jerónimo) comunica necesidades por WhatsApp, correo o llamada.
- No hay un formato fijo ni un lugar centralizado para el registro inicial.

**NT-1:** Se propone centralizar toda solicitud en una nota inicial dentro de la carpeta `00-Pendientes` usando el ID único `REQ-XXX` para evitar el "scope creep" detectado en REQ-07 a REQ-10.

**Propuesta:**
- Samuel Blanco recibe la solicitud y crea un archivo `REQ-XXX - [Titulo].md` en la carpeta `02-Requisitos/00-Pendientes/`.
- El estado inicial es `Pendiente`.

### Paso 2: Revisión Inicial y Especificación (Hacer)

**Actualmente:**
- Los requisitos se anotan en conversaciones sueltas.
- La redacción es narrativa, sin criterios de aceptación medibles ni ID único.
- No hay una reunión periódica para revisar el impacto técnico.

**NT-2:** El uso de la [[TEMPLATE-REQ]] es obligatorio para garantizar que cada requisito incluya criterios BDD (Dado/Cuando/Entonces), esfuerzo estimado y prioridad, alineándose con SWEBOK v4.

**Propuesta:**
- Reunión semanal entre Samuel (Negocio) y Axel (Desarrollo) para detallar la nota.
- Axel aplica la [[TEMPLATE-REQ]] y define los **Criterios de Aceptación Medibles**.
- Se estima el esfuerzo en horas y se asigna prioridad.
- El estado cambia a `Revisado`.

### Paso 3: Validación con el Cliente (Verificar)

**Actualmente:**
- El cliente da el visto bueno verbalmente o por WhatsApp.
- No existe evidencia registrada ni aprobación explícita por escrito.

**NT-3:** Para evitar conflictos sobre costos (como ocurrió con la renta mensual vs extras), toda aprobación debe ser por escrito (correo o captura de pantalla de WhatsApp) y adjuntarse como evidencia.

**Propuesta:**
- Samuel presenta el requerimiento detallado al cliente.
- El cliente aprueba explícitamente el alcance y los criterios.
- Se guarda la evidencia en la carpeta de adjuntos y se vincula en el campo `validacion_evidencia`.
- El estado cambia a `Aprobado`.

### Paso 4: Línea Base y Trazabilidad (Actuar)

**Actualmente:**
- No existe separación entre requisitos pendientes y aprobados; todo está mezclado.
- No hay matriz de trazabilidad que vincule requisitos con diseño o pruebas.

**NT-4:** La segregación de carpetas (`00-Pendientes` -> `01-Aprobados`) actúa como el control de configuración (CMMI-CM), estableciendo la línea base oficial del proyecto.

**Propuesta:**
- Una vez aprobado, el archivo se mueve a `02-Requisitos/01-Aprobados/`.
- Axel actualiza la matriz de trazabilidad (vinculando con casos de prueba en el proceso 5).

---

## 3. Justificación de Mejoras

**NT-1: Centralización en 00-Pendientes con ID único.**
Justificación: Evita la pérdida de información en hilos de conversación y permite rastrear el origen de cada solicitud desde el primer momento, mitigando el crecimiento descontrolado del alcance.

**NT-2: Uso de Plantilla BDD y Criterios Medibles.**
Justificación: Elimina la ambigüedad en las pruebas. Un criterio de aceptación medible permite que tanto el desarrollador como el cliente tengan la misma expectativa de éxito.

**NT-3: Evidencia de Aprobación por Escrito.**
Justificación: Proporciona respaldo legal y técnico ante posibles disputas contractuales sobre qué funcionalidades están incluidas en los pagos acordados.

**NT-4: Segregación de Carpetas (Línea Base).**
Justificación: Facilita la gestión de la configuración y asegura que el equipo de desarrollo solo trabaje sobre requisitos que han sido validados y formalizados.

---

## 4. Métricas de Éxito

- **Tiempo de Ciclo**: ≤ 5 días hábiles desde la captura hasta la aprobación.
- **Calidad de Especificación**: 100% de los requisitos con criterios de aceptación medibles.
- **Formalidad**: 100% de los requisitos aprobados con evidencia adjunta.

---

## 5. Referencias y Documentos de Apoyo

1. [[TEMPLATE-REQ]] - Plantilla Maestra de Requerimiento.
2. [[CL-02_Verificacion_Requerimientos]] - Checklist de Calidad.
3. [[01-Plan_Accion]] - Estrategia temporal del proyecto.
4. SWEBOK v4 KA1 - Software Requirements.

---

## Historial de Cambios

| Versión | Fecha | Autor | Descripción |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-03-19 | Axel Morales | Creación inicial. |
| 2.0 | 2026-05-13 | Gemini CLI | Rediseño completo bajo modelo ETVX, integración de Obsidian+Relay y aplicación de mejoras SQA (NT). |
