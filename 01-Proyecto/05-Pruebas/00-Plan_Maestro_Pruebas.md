---
id: PLAN-01
titulo: Plan Maestro de Pruebas - Sistema Visualizador de Marcos
version: "1.0"
estado: Activo
tipo: Plan de Pruebas
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Samuel Blanco
referencias:
  - SWEBOK v4 KA5 - Testing
  - Lewis - Testing and Quality
  - PROC-05_Plan_Pruebas
tags:
  - pruebas
  - plan
  - calidad
---

# Plan Maestro de Pruebas - Sistema Visualizador de Marcos

## 1. Introduccion

Este documento constituye el Plan Maestro de Pruebas para el sistema "Visualizador de Marcos" del cliente Enmarcame. El plan sigue las directrices del SWEBOK v4 y las mejores prácticas de testing definidas por Lewis.

> **Referencia**: Este plan es parte del [[PROC-05_Plan_Pruebas]] (Proceso 5: Plan de Pruebas).

## 2. Alcance de las Pruebas

### 2.1 Modulos a Probar

| Modulo | Descripcion | Casos de Prueba |
|--------|-------------|------------------|
| **Modulo 1: Carga** | Carga de imagenes del cliente | CP-01 a CP-03 |
| **Modulo 2: Catalogo** | Gestion y visualizacion del catalogo | CP-04 a CP-07 |
| **Modulo 3: Previsualizacion** | Renderizado 3D de marcos | CP-08 a CP-12 |
| **Modulo 4: Pantalla Secundaria** | Proyeccion en pantalla adicional | CP-13 a CP-15 |

### 2.2 Requerimientos a Probar

| REQ | Descripcion | Estado | Casos de Prueba |
|-----|-------------|--------|-----------------|
| REQ-01 | Carga de imagen | Implementado | CP-01, CP-02, CP-03 |
| REQ-02 | Previsualizacion del marco | Implementado | CP-08, CP-09 |
| REQ-03 | Generacion de marcos 3D | Implementado | CP-08, CP-09 |
| REQ-04 | Catalogo de marcos | Implementado | CP-04, CP-05 |
| REQ-05 | Filtrado del catalogo | Implementado | CP-05, CP-06, CP-07 |
| REQ-06 | Datos del catalogo | Implementado | CP-04 |
| REQ-07 | Marcos dobles | Pendiente | CP-09 |
| REQ-08 | Tipos de vidrio | Pendiente | CP-10 |
| REQ-09 | Maria Luisa | Pendiente | CP-11 |
| REQ-10 | Pantalla secundaria | Pendiente | CP-13, CP-14, CP-15 |

## 3. Tipos de Pruebas

### 3.1 Pruebas Funcionales

- **Pruebas de unidad**: Funcionalidad individual de componentes
- **Pruebas de integracion**: Comunicacion entre componentes
- **Pruebas de sistema**: Flujo completo de extremo a extremo
- **Pruebas de regresion**: Verificar que cambios no rompan funcionalidad existente

### 3.2 Pruebas No Funcionales

- **Pruebas de rendimiento**: Tiempo de carga y renderizado
- **Pruebas de usabilidad**: Experiencia de usuario
- **Pruebas de compatibilidad**: Navegadores y dispositivos

## 4. Criterios de Entrada y Salida

### 4.1 Criterios de Entrada

- Requerimientos documentados y approveados
- Entorno de pruebas configurado
- Casos de prueba diseñados
- Datos de prueba preparados

### 4.2 Criterios de Salida

- 100% de casos de prueba ejecutados (para cada modulo)
- Defectos criticos y altos resueltos
- Reporte de resultados generado
- Aprobacion del responsable de calidad

## 5. Matriz de Trazabilidad REQ -> CR -> CP

```
REQ-01 (Carga Imagen)
  └── CP-01: JPG valida
  └── CP-02: Archivo invalido
  └── CP-03: Imagen grande

REQ-02 (Previsualizacion Marco)
  └── CP-08: Marco simple
  └── CP-09: Marco doble

REQ-03 (Generacion Marcos 3D)
  └── CP-08: Marco simple
  └── CP-09: Marco doble

REQ-04 (Catalogo Marcos)
  └── CP-04: Carga catalogo
  └── CP-05: Filtro modelo

REQ-05 (Filtrado Catalogo)
  └── CP-05: Filtro modelo
  └── CP-06: Filtro color
  └── CP-07: Filtro ancho

REQ-06 (Datos Catalogo)
  └── CP-04: Carga catalogo

REQ-07 (Marcos Dobles) - PENDIENTE
  └── CP-09: Marco doble

REQ-08 (Tipo Vidrio) - PENDIENTE
  └── CP-10: Tipo vidrio

REQ-09 (Maria Luisa) - PENDIENTE
  └── CP-11: Maria Luisa

REQ-10 (Pantalla Secundaria) - PENDIENTE
  └── CP-13: Proyeccion
  └── CP-14: Sync tiempo real
  └── CP-15: Fallback sin pantalla
```

## 6. Schedule de Pruebas

| Fase | Modulo | Duracion Estimada | Estado |
|------|--------|-------------------|--------|
| 1 | Modulo 1: Carga | 1 dia | Pendiente |
| 2 | Modulo 2: Catalogo | 1 dia | Pendiente |
| 3 | Modulo 3: Previsualizacion | 2 dias | Pendiente |
| 4 | Modulo 4: Pantalla Secundaria | 1 dia | Pendiente |
| 5 | Pruebas de regresion | 1 dia | Pendiente |

## 7. Recursos

| Rol | Responsable | Disponibilidad |
|-----|-------------|----------------|
| Tester | Axel Morales | Full-time |
| Lider de Pruebas | Samuel Blanco | Part-time |
| Desarrollador | Samuel Blanco/Axel | Soporte |

## 8. Herramientas de Prueba

- **Automatizacion**: Selenium (pruebas E2E), Jest (pruebas unitarias)
- **Gestion**: Obsidian con plugin Dataview (este vault)
- **Reporte**: Markdown con plantillas estandarizadas

## 9. Gestion de Defectos

| Severidad | Descripcion | Tiempo de Resolucion |
|-----------|-------------|----------------------|
| Critica | Sistema no funciona, perdida de datos | 24 horas |
| Alta | Funcionalidad principal afectada | 48 horas |
| Media | Funcionalidad secundaria afectada | 1 semana |
| Baja | Issue cosmético o mejora | 2 semanas |

## 10. Entregables

| Entregable | Descripcion |
|------------|-------------|
| Plan Maestro de Pruebas | Este documento |
| Casos de Prueba | 15 archivos (CP-01 a CP-15) |
| Reporte de Ejecucion | Resultados de pruebas |
| Registro de Defectos | Issues encontrados y resueltos |

## 11. Referencias

- [[PROC-05_Plan_Pruebas]]
- [[02-Convenciones_y_Tags]] - Plantillas de casos de prueba
- [[07-Metricas/01-Registro_Defectos]] - Registro de defectos

---

*Plan creado: 2026-03-23 | Ultima actualizacion: 2026-03-23*
*Referencia: SWEBOK v4 KA5 - Software Testing*