---
id: PROC-02
titulo: Proceso 2 - Especificacion Profunda de Requerimientos
version: "1.0"
estado: Pendiente
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-04-13
responsable: Axel Morales
disparador: Finalizacion del Proceso 1 (linea base aprobada)
criterio_entrada: 01-Propuesta_Recuperada.md con estado "Aprobado por cliente"
criterio_salida: Archivos REQ-XX.md completos para REQ-01 a REQ-10
entradas:
  - 01-Propuesta_Recuperada.md
  - 02-Acuerdos_Cliente.md
  - Lista de requerimientos generales
salidas:
  - REQ-01_Carga_Imagen.md
  - REQ-02_Previsualizacion_Marco.md
  - REQ-03_Generacion_Marcos_3D.md
  - REQ-04_Catalogo_Marcos.md
  - REQ-05_Filtrado_Catalogo.md
  - REQ-06_Datos_Catalogo.md
  - REQ-07_Marcos_Dobles.md
  - REQ-08_Tipo_Vidrio.md
  - REQ-09_Maria_Luisa.md
  - REQ-10_Pantalla_Secundaria.md
actividades:
  - Tomar cada REQ general de la tabla actual
  - Aplicar la plantilla de Requerimiento Profundo a cada uno
  - Para los REQ-07 a REQ-10 (scope creep): crear el CR correspondiente antes de especificar
  - Completar la seccion de Trazabilidad con los CP que se van a crear en Proceso 5
  - Walkthrough informal de los REQ con el cliente para validar los criterios de aceptacion
roles:
  - Axel Morales (especificacion tecnica)
  - Samuel Blanco (validacion de negocio)
referencias_biblio:
  - "SWEBOK v4 KA1 4.5 - Atributos de un requerimiento"
  - "Lewis Cap. 5 - Testing Requirements"
  - "O'Regan Cap. 2 - Inspecciones Fagan"
tags:
  - proceso
  - requerimientos
---
# Proceso 2 — Especificacion Profunda de Requerimientos

> **Fundamentacion**: Segun Daniel Galin (2004), los procedimientos e instrucciones de trabajo son componentes de infraestructura esenciales para la prevencion de errores. Este proceso utiliza la metodologia **ETVX** para garantizar la repetibilidad y el control de calidad en la elicitacion tecnica.

## 1. Estructura del Proceso (ETVX)

| Fase | Definicion | Detalles |
| :--- | :--- | :--- |
| **[E] Entry** | Criterios de Entrada | [[01-Propuesta_Recuperada]] en estado "Aprobado" + [[05-Contrato_Desarrollo]] disponible. |
| **[T] Tasks** | Tareas Operativas | Pasos 2.1 a 2.5 (Ver Seccion 2). |
| **[V] Verification** | Verificacion de Calidad | Aplicacion de [[CL-02_Verificacion_Requerimientos]] + [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/PROC-06_Inspecciones]]. |
| **[X] Exit** | Criterios de Salida | Archivos [[REQ-01]] a [[REQ-10]] con estado "Verificado" y firma del responsable. |

## 2. Instrucciones de Trabajo (Paso a Paso)

### Tarea 2.1: Inicializacion del Artefacto
1.  **Localizar Fuente**: Abra [[01-Propuesta_Recuperada]] e identifique el requerimiento general a detallar.
2.  **Crear Archivo**: En la carpeta `02-Requerimientos/`, cree un archivo con el nombre `REQ-[ID]_[Nombre].md`.
3.  **Aplicar Estructura**: Copie el contenido de [[TEMPLATE-REQ]] en el nuevo archivo.

### Tarea 2.2: Elicitacion Técnica
1.  **Definir Alcance**: Redacte la "Descripcion General" enfocada en el beneficio del usuario.
2.  **Extraer Reglas de Negocio (RN)**: Busque en [[04-Minuta_Entrevista_Recuperacion]] y [[05-Contrato_Desarrollo]] todas las restricciones cuantitativas y listelas como RN-[ID]-XX.
3.  **Trazar Fuente**: En la sección de "Fuente", cree un wikilink al contrato o minuta que justifica la existencia del requerimiento.

### Tarea 2.3: Modelado de Comportamiento
1.  **Flujo Principal**: Escriba los pasos del "Happy Path" en formato Activo (Ej: "El sistema valida...", "El usuario presiona...").
2.  **Analisis de Excepciones**: Identifique al menos 3 posibles fallos (Red, Datos Invalidos, Error de Servidor) y documente la respuesta del sistema.
3.  **Criterios BDD**: Traduzca el flujo principal a escenarios Dado/Cuando/Entonces. **Regla**: Al menos 1 CA (Criterio de Aceptación) por cada flujo alternativo.

### Tarea 2.4: Auto-Verificacion (SQA Individual)
1.  **Ejecutar Checklist**: Abra [[CL-02_Verificacion_Requerimientos]].
2.  **Validar Atributos**: Marque cada item del checklist sobre el REQ recien creado.
3.  **Corregir**: Si un item no se cumple, regrese a la Tarea 2.2 o 2.3.

### Tarea 2.5: Revision por Pares (Inspeccion O'Regan)
1.  **Solicitar Revision**: Envíe el REQ al responsable de validación de negocio (Samuel Blanco).
2.  **Documentar Feedback**: Registre las observaciones en la seccion de "Historial de Cambios" del REQ.
3.  **Cierre**: Una vez solventadas las dudas, cambie el estado del REQ a "Verificado".

## 3. Matriz de Responsabilidades (RACI)

| Tarea | Axel (Tecnico) | Samuel (Negocio) | Cliente |
| :--- | :---: | :---: | :---: |
| T2.1 Inicializacion | **R** | I | I |
| T2.2 Elicitacion | **R** | C | I |
| T2.3 Modelado | **R** | C | I |
| T2.4 Auto-Verificacion | **R** | I | I |
| T2.5 Inspeccion | A | **R** | C |

*(R: Responsable, A: Aprueba, C: Consultado, I: Informado)*

## 3. Plantilla Maestra de Requerimiento

Para garantizar la estandarización, todos los requerimientos deben crearse utilizando la plantilla oficial del proyecto.

- **Plantilla Oficial**: [[TEMPLATE-REQ]]

> **Nota**: La plantilla incluye los atributos obligatorios exigidos por SWEBOK v4 KA1 §4.5 (Identificador, Fuente, Prioridad, Criterios de Aceptación, etc.). No se permiten modificaciones a la estructura de la plantilla sin un Change Request aprobado.

## 4. Lista de Requerimientos a Especificar

### Requerimientos Originales (Implementados)

| ID     | Titulo                     | Estado Actual |
| :----- | :------------------------- | :------------ |
| REQ-01 | Carga de Imagen            | Implementado  |
| REQ-02 | Previsualizacion del Marco | Implementado  |
| REQ-03 | Generacion de Marcos 3D    | Implementado  |
| REQ-04 | Catalogo de Marcos         | Implementado  |
| REQ-05 | Filtrado del Catalogo      | Implementado  |
| REQ-06 | Datos del Catalogo         | Implementado  |

### Requerimientos Nuevos (Pendientes)

| ID     | Titulo               | Estado Actual | Requiere CR |
| :----- | :------------------- | :------------ | :---------- |
| REQ-07 | Marcos Dobles        | Pendiente     | CR-01       |
| REQ-08 | Tipo de Vidrio       | Pendiente     | CR-02       |
| REQ-09 | Maria Luisa Multiple | Pendiente     | CR-03       |
| REQ-10 | Pantalla Secundaria  | Pendiente     | CR-04       |

## 5. Atributos de Requerimiento por Completar

Segun SWEBOK v4 KA1 §4.5, cada requerimiento debe incluir:

| Atributo                | Descripcion                     | Obligatorio |
| :---------------------- | :------------------------------ | :---------- |
| Identificador           | Codigo unico del requerimiento  | Si          |
| Titulo                  | Nombre descriptivo              | Si          |
| Descripcion             | Que debe hacer el sistema       | Si          |
| Reglas de Negocio       | Restricciones del negocio       | Si          |
| Precondiciones          | Estado inicial requerido        | Si          |
| Flujo Principal         | Secuencia ideal de pasos        | Si          |
| Flujos Alternativos     | Variaciones del flujo principal | Si          |
| Flujos de Excepcion     | Manejo de errores               | Si          |
| Criterios de Aceptacion | Condiciones de aceptacion (BDD) | Si          |
| Restricciones Tecnicas  | Limitaciones tecnicas           | Si          |
| Dependencias            | Requerimientos relacionados     | Si          |
| Prioridad               | Importancia del requerimiento   | Si          |
| Tipo                    | Funcional/No Funcional          | Si          |
| Estado                  | Estado actual del requerimiento | Si          |
| Fuente                  | Origen del requerimiento        | Si          |
| Responsable             | Persona a cargo                 | Si          |
| Version                 | Version del requerimiento       | Si          |
| Historico               | Registro de cambios             | Si          |

## 6. Criterios de Aceptacion del Proceso

- [[REQ- REQ-06 especificados completamente]]
- [ ] CR-01 a CR-04 creados para REQ-07 a REQ-10
- [ ] REQ-07 a REQ-10 especificados completamente
- [ ] Todos los REQ tienen criterios de aceptacion en formato BDD
- [ ] Trazabilidad completa (REQ -> CP -> CR)
- [ ] Walkthrough con cliente completado
- [ ] Proceso cerrado con estado = "Completado"

## 7. Dependencias

- **Pre-requisito**: [[PROC-01_Recuperacion_Linea_Base]] (Proporciona linea base aprobada para especificar REQ sin conflictos)
- **Post-requisito**: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/PROC-03_Control_Cambios]] (Gestiona cambios en REQ especificados), [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/PROC-05_Plan_Pruebas]] (Crea casos de prueba basados en REQ detallados)

## 8. Referencias

- [[01-Proceso_Gobernanza_Vault]]
- [[02-Convenciones_y_Tags]]
- [[PROC-01_Recuperacion_Linea_Base]]

## 9. Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-03-19 | Axel Morales | Creacion inicial |
| 1.1 | 2026-04-13 | Kilo-SQA-Agent | Agregadas justificaciones WHY/HOW en definicion, actividades y dependencias |
| 1.2 | 2026-05-06 | Gemini-SQA-Agent | Sistematizacion completa del proceso usando el modelo ETVX fundamentado en Daniel Galin. Agregada matriz RACI e instrucciones de trabajo paso a paso. |

---

*Proceso creado: 2026-03-19 | Ultima actualizacion: 2026-04-14*
