# Matriz de Trazabilidad de Requisitos — Visualizador de Marcos

**Responsable:** Analista de Requerimientos  
**Entradas:** Requisitos aprobados y pendientes, diseño del sistema y casos de prueba del SGC.  
**Salidas:** Matriz de Trazabilidad de Requisitos (RTM) unificada y sincronizada bidireccionalmente.  

---

## 1. Propósito y Guía de Operación

Esta matriz asegura y demuestra el cumplimiento de la práctica específica **CMMI-DEV v2.0 REQM SP 1.4** (*Mantener trazabilidad bidireccional de los requisitos*). Vincula cada requerimiento de software con su fuente de origen, el diagrama de diseño lógico o físico que lo modela y los casos de prueba de caja negra que verifican su comportamiento funcional en producción.

---

## 2. Tabla de Trazabilidad Bidireccional (RTM)

| ID Requisito | Título del Requisito | Fuente de Origen | Diseño Relacionado | Casos de Prueba Relacionados | Estado |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `REQ-01` | Carga de Imagen de Fondo | `[[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|Contrato de Desarrollo]]` | `[[03-Diseño/01-Ingenieria_Diseño/01-STD-04_Diagrama_Componentes|STD-04 Diagrama de Componentes]]` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/01-CP-01_JPG_valida|CP-01 JPG Valida]]`, `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/02-CP-02_Archivo_invalido|CP-02 Archivo Invalido]]`, `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/03-CP-03_Imagen_grande|CP-03 Imagen Grande]]` | Aprobado |
| `REQ-02` | Previsualización de Imagen con Marco | `[[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|Contrato de Desarrollo]]` | `[[03-Diseño/01-Ingenieria_Diseño/02-STD-05_Flujo_Sistema|STD-05 Flujo del Sistema]]` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/01-CP-08_Marco_simple|CP-08 Marco Simple]]`, `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/05-CP-12_Proporciones|CP-12 Proporciones]]` | Aprobado |
| `REQ-03` | Generación Marcos 3D (obsoleto) | `[[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|Contrato de Desarrollo]]` | `[[03-Diseño/01-Ingenieria_Diseño/03-STD-06_Modelo_Datos|STD-06 Modelo de Datos]]` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/01-CP-08_Marco_simple|CP-08 Marco Simple]]` | Aprobado |
| `REQ-04` | Catálogo de Marcos Disponibles | `[[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|Contrato de Desarrollo]]` | `[[03-Diseño/01-Ingenieria_Diseño/04-STD-07_Arquitectura_Python|STD-07 Arquitectura Python]]` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/01-CP-04_Carga_catalogo|CP-04 Carga Catálogo]]` | Aprobado |
| `REQ-05` | Filtrado del Catálogo de Marcos | `[[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|Contrato de Desarrollo]]` | `[[03-Diseño/01-Ingenieria_Diseño/04-STD-07_Arquitectura_Python|STD-07 Arquitectura Python]]` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/02-CP-05_Filtro_modelo|CP-05 Filtro Modelo]]`, `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/03-CP-06_Filtro_color|CP-06 Filtro Color]]`, `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/04-CP-07_Filtro_ancho|CP-07 Filtro Dimensiones]]` | Aprobado |
| `REQ-06` | Datos del Catálogo | `[[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo|Contrato de Desarrollo]]` | `[[03-Diseño/01-Ingenieria_Diseño/03-STD-06_Modelo_Datos|STD-06 Modelo de Datos]]` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/01-CP-04_Carga_catalogo|CP-04 Carga Catálogo]]` | Aprobado |
| `REQ-07` | Visualización de Marcos Dobles | `[[05-Revisiones e inspecciones/01-Ingenieria_Control/08-CR-01_Marcos_Dobles|CR-01 Marcos Dobles]]` | `[[03-Diseño/01-Ingenieria_Diseño/01-STD-04_Diagrama_Componentes|STD-04 Diagrama de Componentes]]` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/02-CP-09_Marco_doble|CP-09 Marco Doble]]` | Aprobado |
| `REQ-08` | Selección de Tipo de Vidrio | `[[05-Revisiones e inspecciones/01-Ingenieria_Control/09-CR-02_Tipos_Vidrio|CR-02 Tipos de Vidrio]]` | `TBD` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/03-CP-10_Tipo_vidrio|CP-10 Tipo Vidrio]]` | Pendiente |
| `REQ-09` | Simulación de María Luisa | `[[05-Revisiones e inspecciones/01-Ingenieria_Control/10-CR-03_Maria_Luisa|CR-03 María Luisa]]` | `TBD` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Previsualizacion/04-CP-11_Maria_Luisa|CP-11 María Luisa]]` | Pendiente |
| `REQ-10` | Proyección en Pantalla Secundaria | `[[05-Revisiones e inspecciones/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]]` | `TBD` | `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Pantalla_Secundaria/01-CP-13_Proyeccion|CP-13 Apertura Pantalla Sec.]]`, `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Pantalla_Secundaria/02-CP-14_Sync_tiempo_real|CP-14 Sincronización Render]]`, `[[04-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Pantalla_Secundaria/03-CP-15_Fallback_sin_pantalla|CP-15 Desconexión Pantalla]]` | Pendiente |

---

## 3. Control de Entregables Generados

A continuación se detalla la gobernanza del presente documento de trazabilidad:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Matriz de Trazabilidad de Requisitos (RTM) | STD-03-RTM | CMMI-DEV v2.0 - REQM SP 1.4 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.