---
id: ENT-01
titulo: Guia de Entrevista - Proyecto Visualizador de Marcos
version: "1.0"
estado: Activo
tipo: Plantilla
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-25
responsable: Axel Adolfo Morales Caro
entrevistados:
  - Jose Samuel Blanco Cervera
  - Axel Adolfo Morales Caro
  - Cliente (Enmarcame)
referencias:
  - SWEBOK v4 KA2 - Requisitos y Elicitación
  - O'Regan - A Practical Approach to Software Quality - Cap. 2
tags:
  - elicitación
  - entrevista
  - requisitos
  - baseline
---

# Guia de Entrevista - Proyecto Visualizador de Marcos

> Esta guía de entrevista está diseñada para elicitar y documentar los requisitos del proyecto Visualizador de Marcos para el cliente "Enmarcame". La entrevista se basa en la metodología de elicitación de requisitos del SWEBOK v4 y las mejores prácticas de calidad de software.

---

## 1. Objetivos de la Entrevista

### 1.1 Objetivo General
Reconstruir y documentar el alcance completo del proyecto Visualizador de Marcos, incluyendo los requisitos originales y los nuevos requerimientos que han surgido (scope creep), para establecer una línea base sólida que permita el control de cambios y la gestión de calidad.

### 1.2 Objetivos Específicos
- **Objetivo 1:** Establecer el contexto del proyecto y la propuesta original acordada
- **Objetivo 2:** Documentar los requisitos funcionales implementados (REQ-01 a REQ-06)
- **Objetivo 3:** Analizar los nuevos requisitos pendientes (REQ-07 a REQ-10) y su impacto
- **Objetivo 4:** Identificar el modelo de negocio, estructura de costos y acuerdos económicos
- **Objetivo 5:** Capturar la visión técnica y arquitectura del sistema
- **Objetivo 6:** Documentar expectativas de calidad y métricas de éxito

---

## 2. Perfil de los Entrevistados

### 2.1 Entrevistado Principal: Jose Samuel Blanco Cervera
- **Rol:** Líder técnico y gestor del proyecto
- **Conocimiento esperado:** Propuesta original, decisiones técnicas, acuerdos con el cliente, arquitectura del sistema
- **Duración estimada:** 90-120 minutos

### 2.2 Entrevistado Secundario: Axel Adolfo Morales Caro
- **Rol:** Desarrollador ySupport técnico
- **Conocimiento esperado:** Implementación técnica, catálogos de marcos, proceso de escaneo, detalles de base de datos
- **Duración estimada:** 60-90 minutos

### 2.3 Entrevistado terciario: Cliente (Enmarcame)
- **Rol:** Dueño del negocio y usuario final
- **Conocimiento esperado:** Requisitos de negocio, flujos de trabajo, expectativas de uso, nuevos requerimientos
- **Duración estimada:** 60-90 minutos

---

## 3. Bloques Tematicos

### Bloque A: Contexto y Origen del Proyecto

**Objetivo:** Establecer el contexto inicial del proyecto, cómo surgió la oportunidad y quiénes fueron los involucrados clave.

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo REQ |
|----|-----------|----------|------|--------------|
| A.1 | Origen | ¿Cómo se originó el contacto con el cliente "Enmarcame"? ¿Fue a través de una recomendación, publicidad, o contacto directo? | Abierta | - |
| A.2 | Origen | ¿Cuál fue la necesidad específica que el cliente expresó inicialmente? ¿Qué problema quería resolver? | Abierta | - |
| A.3 | Origen | ¿Quiénes participaron en las primeras reuniones con el cliente? ¿Solo tú, o incluía a Axel desde el inicio? | Abierta | - |
| A.4 | Origen | ¿Cuál era el plazo original acordado para el proyecto? ¿Se ha modificado desde entonces? | Abierta | - |
| A.5 | Origen | ¿Existió alguna propuesta formal inicial? Si es así, ¿puedes reconstruir los puntos principales? | Abierta | - |

#### Notas de Seguimiento
- Documentar nombres de todos los contactos del cliente
- Capturar fechas aproximadas de las primeras reuniones
- Identificar si hubo propuestas escritas o fue todo verbal

---

### Bloque B: Alcance del Proyecto - Requisitos Originales

**Objetivo:** Documentar el alcance original del proyecto tal como fue acordado al inicio, antes de cualquier expansión (scope creep).

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo REQ |
|----|-----------|----------|------|--------------|
| B.1 | Alcance | ¿Cuál era la descripción del producto mínimo viable (MVP) acordado con el cliente? | Abierta | REQ-01, REQ-02 |
| B.2 | Alcance | ¿Qué funcionalidades debía incluir obligatoriamente el sistema desde el inicio? | Abierta | REQ-01 a REQ-06 |
| B.3 | Alcance | ¿El cliente solicitó alguna funcionalidad que NO se implementó en la versión inicial? ¿Por qué? | Abierta | - |
| B.4 | Alcance | ¿Cuáles fueron los criterios de aceptación definidos para considerar "completo" el proyecto? | Abierta | - |
| B.5 | Alcance | ¿Se definió algún requisito no funcional específico (rendimiento, seguridad, usabilidad)? | Abierta | - |

#### Matriz de Requisitos Originales

```
| REQ ID | Descripcion Original | Estado Actual | Evidencia |
|--------|---------------------|---------------|-----------|
| REQ-01 | El cliente puede subir una foto desde la app web | Implementado | - |
| REQ-02 | El sistema muestra una previsualizacion del marco sobre la foto | Implementado | - |
| REQ-03 | Los marcos se crean desde una textura escaneada y un modelado 3D | Implementado | - |
| REQ-04 | El cliente puede seleccionar marcos desde un catalogo | Implementado | - |
| REQ-05 | (Por verificar) | - | - |
| REQ-06 | El catalogo incluye: ancho, alto, clave, textura, forma 3D | Implementado | - |
```

#### Notas de Seguimiento
- Comparar la propuesta inicial con la implementación actual
- Identificar errores entre lo acordado y lo implementado

---

### Bloque C: Requisitos Nuevos y Scope Creep

**Objetivo:** Documentar los nuevos requerimientos que surgieron después del lanzamiento inicial, analyzing su impacto y el proceso de gestión de cambios.

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo REQ |
|----|-----------|----------|------|--------------|
| C.1 | Scope Creep | ¿Cuándo surgieron los nuevos requerimientos (REQ-07 a REQ-10)? ¿Fueron antes o después del lanzamiento? | Abierta | REQ-07 a REQ-10 |
| C.2 | Scope Creep | ¿Quién solicitó los nuevos requerimientos? ¿Fue el cliente directamente, o a través de un intermediario? | Abierta | REQ-07 a REQ-10 |
| C.3 | Scope Creep | ¿Estos nuevos requerimientos pasaron por algún proceso formal de aprobación de cambios? | Si/No | REQ-07 a REQ-10 |
| C.4 | Scope Creep | ¿Se estimó el impacto en tiempo y costo para cada nuevo requerimiento? | Abierta | CR-01 a CR-04 |
| C.5 | Scope Creep | ¿El cliente aceptó formalmente los cambios propuestos? | Si/No | CR-01 a CR-04 |

#### Detalle de Cambios Registrados

```
CR-01: Marcos Dobles
- Fecha de solicitud: [por documentar]
- Solicitado por: [por documentar]
- Descripcion: Sistema debe soportar dos marcos simultaneos
- Impacto estimado: [por estimar]
- Estado: Pendiente

CR-02: Tipos de Vidrio
- Fecha de solicitud: [por documentar]
- Solicitado por: [por documentar]
- Descripcion: Cliente puede seleccionar tipo de vidrio
- Impacto estimado: [por estimar]
- Estado: Pendiente

CR-03: Tipos de Maria Luisa
- Fecha de solicitud: [por documentar]
- Solicitado por: [por documentar]
- Descripcion: Cliente puede seleccionar diferentes maria luisas
- Impacto estimado: [por estimar]
- Estado: Pendiente

CR-04: Pantalla Secundaria
- Fecha de solicitud: [por documentar]
- Solicitado por: [por documentar]
- Descripcion: Proyeccion en pantalla secundaria para previsualizacion
- Impacto estimado: [por estimar]
- Estado: Pendiente
```

#### Notas de Seguimiento
- Identificar el patrón de cómo llegan los nuevos requerimientos
- Documentar la comunicación informal vs formal
- Evaluar el impacto en la relación con el cliente

---

### Bloque D: Modelo de Negocio y Estructura de Costos

**Objetivo:** Documentar el acuerdo financiero original y cualquier modificación posterior.

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo |
|----|-----------|----------|------|----------|
| D.1 | Costo | ¿Cuál fue el costo total acordado inicialmente para el proyecto? | Abierta | Costo |
| D.2 | Costo | ¿Se definió un costo recurrente (renta, mantenimiento)? ¿Cuál es el monto? | Abierta | Costo |
| D.3 | Costo | ¿Los nuevos requerimientos implican costos adicionales? ¿Se ha comunicado al cliente? | Abierta | CR-01 a CR-04 |
| D.4 | Costo | ¿Existe un contrato formal o fue todo acuerdo verbal? | Abierta | Legal |
| D.5 | Costo | ¿Qué incluye exactamente el costo de $24,000 MXN inicial? | Abierta | Alcance |

#### Estructura de Costos Documentada

```
Costo Inicial: $24,000 MXN
Costo Recurrente: $2,500 MXN / mes (renta del sistema)

Desglose estimado:
- Desarrollo del sistema: [por documentar]
- Escaneo de marcos: [por documentar]
- Configuracion e implementacion: [por documentar]
- Capacitacion: [por documentar]
```

#### Notas de Seguimiento
- Verificar si hay facturas o recibos que respalden los acuerdos
- Documentar cualquier promesa de costo adicionales
- Identificar expectativas del cliente sobre costos futuros

---

### Bloque E: Arquitectura Tecnica y Stack Tecnologico

**Objetivo:** Documentar la arquitectura técnica del sistema, decisiones de diseño y dependencias.

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo |
|----|-----------|----------|------|----------|
| E.1 | Tecnica | ¿Cuál es el stack tecnológico completo del sistema? (Frontend, Backend, DB, herramientas) | Abierta | Arquitectura |
| E.2 | Tecnica | ¿Por qué se eligió esta tecnología específica? ¿Hubo alguna evaluación de alternativas? | Abierta | Arquitectura |
| E.3 | Tecnica | ¿El sistema tiene una API? ¿Qué endpoints expose? | Abierta | Arquitectura |
| E.4 | Tecnica | ¿Dónde está hosteado el sistema? ¿Quién mantiene la infraestructura? | Abierta | Operaciones |
| E.5 | Tecnica | ¿Cuál es el proceso de despliegue? ¿Es manual o automatizado? | Abierta | DevOps |

#### Detalle Tecnico

```
Frontend: HTML5, Bootstrap, CSS, JavaScript
Backend: [por documentar]
Base de Datos: PostgreSQL
Herramientas Auxiliares:
  - Python (deteccion de ancho de marcos)
  - [otras herramientas]

Infraestructura:
- Hosting: [por documentar]
- Dominio: [por documentar]
- Certificados SSL: [por documentar]
```

#### Notas de Seguimiento
- Identificar dependencias críticas
- Documentar limitaciones técnicas actuales
- Evaluar necesidad de refactoring

---

### Bloque F: Flujo de Trabajo y Procesos de Negocio

**Objetivo:** Documentar cómo el cliente usa el sistema en su operación diaria.

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo |
|----|-----------|----------|------|----------|
| F.1 | Operacion | ¿Cómo es el flujo típico de un cliente en la tienda usando el sistema? | Abierta | UX |
| F.2 | Operacion | ¿Quién opera el sistema en la tienda? ¿El cliente directamente o hay empleados? | Abierta | UX |
| F.3 | Operacion | ¿Cuántos marcos tiene el catálogo actualmente? ¿Se agregan nuevos marcos frecuentemente? | Abierta | REQ-04 |
| F.4 | Operacion | ¿El sistema está integrado con algún otro sistema (POS, inventario)? | Abierta | Integracion |
| F.5 | Operacion | ¿Hay algún proceso de mantenimiento del sistema? ¿Quién lo realiza? | Abierta | Mantenimiento |

#### Flujo de Usuario Documentado

```
1. Cliente llega a la tienda
2. Empleado abre la aplicacion web
3. Cliente sube su foto desde el dispositivo
4. Cliente selecciona un marco del catalogo
5. Sistema muestra previsualizacion 3D
6. Cliente repite hasta encontrar el marco deseado
7. [Si aplica] Selecciona tipo de vidrio
8. [Si aplica] Selecciona Maria Luisa
9. Finaliza la seleccion
```

#### Notas de Seguimiento
- Identificar puntos de fricción en la experiencia de usuario
- Documentar sugerencias de mejora del cliente
- Evaluar necesidades de capacitación

---

### Bloque G: Calidad y Expectativas

**Objetivo:** Documentar las expectativas de calidad del cliente y métricas de éxito.

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo |
|----|-----------|----------|------|----------|
| G.1 | Calidad | ¿Qué define el cliente como un "sistema exitoso"? | Abierta | Metricas |
| G.2 | Calidad | ¿Ha tenido problemas con el sistema desde que esta en produccion? | Abierta | Issues |
| G.3 | Calidad | ¿Qué tan importante es el rendimiento (velocidad) del sistema para el cliente? | Abierta | NF |
| G.4 | Calidad | ¿El cliente ha solicitado alguna funcionalidad de reporte o analytics? | Abierta | REQ-10 |
| G.5 | Calidad | ¿Hay alguna expectativa especifica sobre disponibilidad (uptime)? | Abierta | NF |

#### Metricas de Exito Sugeridas

```
- Tiempo de carga de pagina: < 3 segundos
- Tiempo de renderizado 3D: < 2 segundos
- Disponibilidad: 99.5%
- Satisfaccion del cliente: Encuesta trimestral
- Numero de defectos: < 5 criticos en produccion
```

#### Notas de Seguimiento
- Documentar incidentes reportados por el cliente
- Identificar expectativas no expresadas
- Establecer baseline para mejoras futuras

---

### Bloque H: Cambios Futuros y Roadmap

**Objetivo:** Documentar la visión a futuro del sistema y posibles expansiones.

#### Preguntas de Elicitacion

| ID | Categoria | Pregunta | Tipo | Objetivo |
|----|-----------|----------|------|----------|
| H.1 | Roadmap | ¿El cliente ha mencionado caracteristicas que le gustaria tener en el futuro? | Abierta | Vision |
| H.2 | Roadmap | ¿Hay planes de expandir el sistema a otras ubicaciones o franquicias? | Abierta | Expansion |
| H.3 | Roadmap | ¿El cliente requiere integracion con redes sociales o tienda en linea? | Abierta | Integracion |
| H.4 | Roadmap | ¿Existe alguna fecha limite para implementar los requerimientos pendientes? | Abierta | Cronograma |
| H.5 | Roadmap | ¿Cuál es la prioridad relativa de los REQ-07 a REQ-10? | Abierta | Prioridad |

#### Notas de Seguimiento
- Identificar oportunidades de negocio adicionales
- Documentar competidores o alternativas que el cliente conoce
- Establecer proceso formal para nuevos requerimientos

---

## 4. Formato de Registro de Respuestas

### 4.1 Plantilla por Sesion

```
## Sesion de Entrevista - [Fecha]
**Entrevistado:** [Nombre]
**Entrevistador:** [Nombre]
**Duracion:** [HH:MM]
**Tipo:** Presencial / Remota / Telefonica

### Respuestas Registradas

| Pregunta | Respuesta | Observaciones |
|----------|-----------|---------------|
| | | |

### Hallazgos Clave
- [Punto 1]
- [Punto 2]

### Acciones de Seguimiento
- [Accion 1]
- [Accion 2]
```

### 4.2 Checklist de Completitud

```
[x] Bloque A: Contexto y Origen - Completado
[x] Bloque B: Alcance Original - Completado
[x] Bloque C: Scope Creep - Completado
[x] Bloque D: Costos - Completado
[x] Bloque E: Arquitectura - Completado
[x] Bloque F: Operacion - Completado
[x] Bloque G: Calidad - Completado
[x] Bloque H: Roadmap - Completado
```

---

## 5. Materiales de Referencia

### 5.1 Documentos Relacionados
- [[01-Baseline/00-PROC-01_Recuperacion_Linea_Base]] - Proceso de recuperación de línea base
- [[02-Requerimientos/PROC-02_Especificacion_Requerimientos]] - Especificación de requisitos
- [[03-Control_Cambios/PROC-03_Control_Cambios]] - Registro de cambios (CR-01 a CR-04)
- [[PROC-04_Arquitectura_Sistema]] - Documentación de arquitectura
- [[PROC-05_Plan_Pruebas]] - Plan de pruebas

### 5.2 Referencias Bibliograficas
- SWEBOK v4, KA2 - Requisitos y Elicitación
- O'Regan, G. (2022). A Practical Approach to Software Quality. Cap. 2: Requirements Engineering
- IEEE 830 - Software Requirements Specifications

---

## 6. Aprobacion y Control

| Version | Fecha | Autor | Cambios |
|---------|-------|-------|---------|
| 1.0 | 2026-03-23 | Axel Adolfo Morales Caro | Creacion inicial |

### Responsables
- **Elaboro:** Axel Adolfo Morales Caro
- **Reviso:** Jose Samuel Blanco Cervera
- **Aprobo:** [Pendiente]

---

*Documento creado como parte del proceso de recuperación de línea base (PROC-01)*
*Renombrado: 03-Guia_Entrevista_Samuel.md (original: Guia_Entrevista_Proyecto.md)*
*Ultima actualizacion: 2026-03-25*