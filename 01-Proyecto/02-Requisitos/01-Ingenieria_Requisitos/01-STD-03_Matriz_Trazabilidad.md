# Matriz de Trazabilidad de Requisitos — Visualizador de Marcos

**Responsable:** Analista de Requerimientos  
**Entradas:** Requisitos aprobados y pendientes, diseño del sistema y casos de prueba del SGC.  
**Salidas:** Matriz de Trazabilidad de Requisitos (RTM) unificada y sincronizada bidireccionalmente.  

---

## 1. Propósito y Guía de Operación

**CMMI-DEV v2.0 REQM SP 1.4**  *Mantener trazabilidad bidireccional de los requisitos*
Vincula cada requesito  de software con su fuente de origen, el diagrama de diseño lógico o físico que lo modela y los casos de prueba de caja negra que verifican su comportamiento funcional en producción.

---

## 2. Tabla de Trazabilidad Bidireccional (RTM)

| ID Requisito | Título del Requisito | Fuente de Origen | Diseño Relacionado | Casos de Prueba Relacionados | Estado |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [[01-REQ-01_Carga_Imagen]] | Carga de Imagen de Fondo | [[06-Contrato_Desarrollo]] | [[01-STD-04_Diagrama_Componentes]] | [[01-CP-01_JPG_valida]], [[02-CP-02_Archivo_invalido]], [[03-CP-03_Imagen_grande]] | Aprobado |
| [[05-REQ-02_Previsualizacion_Marco]] | Previsualización de Imagen con Marco | [[06-Contrato_Desarrollo]] | [[02-STD-05_Flujo_Sistema]] | [[01-CP-08_Marco_simple]], [[05-CP-12_Proporciones]] | Aprobado |
| [[06-REQ-03_Generacion_Marcos_3D]] | Generación Marcos 3D (obsoleto) | [[06-Contrato_Desarrollo]] | [[03-STD-06_Modelo_Datos]] | [[01-CP-08_Marco_simple]] | Aprobado |
| [[02-REQ-04_Catalogo_Marcos]] | Catálogo de Marcos Disponibles | [[06-Contrato_Desarrollo]] | [[04-STD-07_Arquitectura_Python]] | [[01-CP-04_Carga_catalogo]] | Aprobado |
| [[03-REQ-05_Filtrado_Catalogo]] | Filtrado del Catálogo de Marcos | [[06-Contrato_Desarrollo]] | [[04-STD-07_Arquitectura_Python]] | [[02-CP-05_Filtro_modelo]], [[03-CP-06_Filtro_color]], [[04-CP-07_Filtro_ancho]] | Aprobado |
| [[04-REQ-06_Datos_Catalogo]] | Datos del Catálogo | [[06-Contrato_Desarrollo]] | [[03-STD-06_Modelo_Datos]] | [[01-CP-04_Carga_catalogo]] | Aprobado |
| [[07-REQ-07_Marcos_Dobles]] | Visualización de Marcos Dobles | [[08-CR-01_Marcos_Dobles]] | [[01-STD-04_Diagrama_Componentes]] | [[02-CP-09_Marco_doble]] | Aprobado |
| [[08-REQ-08_Tipo_Vidrio]] | Selección de Tipo de Vidrio | [[09-CR-02_Tipos_Vidrio]] | TBD | [[03-CP-10_Tipo_vidrio]] | Pendiente |
| [[09-REQ-09_Maria_Luisa]] | Simulación de María Luisa | [[10-CR-03_Maria_Luisa]] | TBD | [[04-CP-11_Maria_Luisa]] | Pendiente |
| [[10-REQ-10_Pantalla_Secundaria]] | Proyección en Pantalla Secundaria | [[11-CR-04_Pantalla_Secundaria]] | TBD | [[01-CP-13_Proyeccion]], [[02-CP-14_Sync_tiempo_real]], [[03-CP-15_Fallback_sin_pantalla]] | Pendiente |

---

## 3. Control de Entregables Generados

A continuación se detalla la gobernanza del presente documento de trazabilidad:

| Artefacto Generado | Código | Estándar de Respaldo | Estado |
|---|---|---|---|
| Matriz de Trazabilidad de Requisitos (RTM) | STD-03-RTM | CMMI-DEV v2.0 - REQM SP 1.4 | Vigente e Incorporado al SGC |

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.