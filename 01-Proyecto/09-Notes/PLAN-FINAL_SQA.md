---
id: NOTE-PLAN-FINAL
titulo: Plan de Trabajo de SQA - Entrega Final Proyecto
version: "3.0"
estado: Activo
tipo: Plan_Trabajo
fecha_creacion: 2026-05-12
responsables: [Axel Morales, Samuel Blanco, Carlos Yonson]
referencias:
  - "Galin - Software Quality Assurance"
  - "Nuevo Ciclo de Vida: 8 Procesos (Incluye Despliegue)"
tags:
  - notes/plan
  - sqa/entrega-final
---

# Plan de Trabajo: Finalizacion del Plan de Aseguramiento Completo (V3)

> **Objetivo**: Consolidar el SGC del proyecto "Visualizador de Marcos" bajo la estructura de 8 fases, con responsabilidades claras por integrante.

## 1. Distribucion de Responsabilidades (Fuerza de Tarea)

### Integrante 1: Samuel Blanco (Implementacion y Operaciones)
*   **Fase 04-Codificacion**: Implementacion tecnica y modulos Python (COD).
*   **Fase 06-Mantenimiento**: Estrategia de soporte y evolucion post-entrega (MNT).
*   **Fase 08-Despliegue**: Puesta en produccion, manuales de usuario y entrega final (DESP).

### Integrante 2: Carlos Yonson (Analisis y Calidad)
*   **Fase 02-Requisitos**: Definicion de REQ-01 a REQ-10 y criterios de aceptacion.
*   **Fase 07-Control**: SCM, Change Requests (CR), Inspecciones y Metricas de Calidad (CTRL).
*   **Entregable**: Reporte de Inspeccion Formal de Requerimientos.

### Integrante 3: Axel Morales (Estrategia y Verificacion)
*   **Fase 00-Meta (Auditoria Normativa)**:
    1.  **Checklist de Cumplimiento ETVX**: Revisar que los 8 archivos `00-PROC-XX` tengan criterios de entrada/salida vinculados a archivos reales, no teoricos.
    2.  **Sincronizacion de Tags**: Verificar que Samuel y Carlos usen el tag `#estado/verificado` solo despues de pasar la checklist `CL-02`.
*   **Fase 01-Linea_Base (Contexto Real)**:
    1.  **Narrativa del Cliente**: Redactar la historia de "Enmarcame", el problema del desperdicio de banak por malas medidas y la necesidad de precision digital.
*   **Fase 03-Diseño (Arquitectura de Precision)**:
    1.  **DIS-01 Diagrama de Modulos**: Detallar la interaccion entre OpenCV (deteccion) y Pillow (renderizado de marcos).
    2.  **DIS-02 Flujo de Datos**: Mapear el viaje del pixel desde la carga de imagen hasta la pantalla secundaria (REQ-10).
*   **Fase 05-Pruebas (Evidencia Empirica)**:
    1.  **CP-01 al CP-15 Ejecucion**: Ejecutar los casos y capturar errores reales (ej: "El script fallo al intentar leer un PNG sin canal alfa").
    2.  **Reporte de Defectos**: Documentar al menos 3 "bugs" encontrados durante el desarrollo y su solucion (esto es lo que mas puntua el profe).
*   **Fase 07-Control (Matriz de Trazabilidad)**:
    1.  **RTM (Matriz de Trazabilidad)**: Crear la tabla que conecte: `REQ-01` -> `DIS-01` -> `COD-Func_Carga` -> `CP-01`. (Esto mata cualquier "hueco").

---

## 2. Nueva Estructura del Ciclo de Vida (SGC)

1.  **00-Meta**: Gobernanza y Estandares.
2.  **01-Linea_Base**: Contexto y Acuerdos.
3.  **02-Requisitos**: Especificacion (REQ).
4.  **03-Diseño**: Arquitectura (DIS).
5.  **04-Codificacion**: Implementacion (COD).
6.  **05-Pruebas**: Verificacion y Validacion (CP).
7.  **06-Mantenimiento**: Soporte (MNT).
8.  **07-Control**: Gestion de Calidad (CTRL).
9.  **08-Despliegue**: Entrega Final (DESP).

---

## 3. Acciones Inmediatas (Checklist de Cumplimiento)

- [ ] **Tarea 01**: (Axel) Revisar que `05-Pruebas` tenga evidencia real del prototipo.
- [ ] **Tarea 02**: (Carlos) Consolidar los resumenes de sesiones de clase en `07-Control`.
- [ ] **Tarea 03**: (Samuel) Crear el primer borrador de `08-Despliegue/DESP-01_Guia_Instalacion.md`.

---

## 4. Cronograma de Emergencia

| Fecha | Hito | Estado |
| :--- | :--- | :---: |
| 12-May | Reestructuracion Final de Roles y Fases | 🟢 |
| 13-May | Cierre de Pruebas y Codificacion | 🟡 |
| 14-May | Auditoria de Calidad y Entrega Presencial | ⚪ |
