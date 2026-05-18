---
id: PROC-03
titulo: Ingeniería Inversa y Diseño de Arquitectura -- XookTech
version: "7.0"
estado: Activo
tipo: Proceso
responsable: Axel Morales (Analista Técnico)
tags:
  - fase/diseño
  - xooktech/proceso
---

# Ingeniería Inversa y Diseño de Arquitectura -- XookTech

**Área de proceso:** 03-Diseño
**Nombre del proceso:** Ingeniería Inversa y Diseño de Arquitectura
**Responsable:** Axel Morales (Analista Técnico)
**Entradas:** 
- Repositorio GitHub: [Marcos2](https://github.com/Bigsami89/Marcos2)
- Requerimientos validados: [[02-Requisitos/01-Ingenieria_Artefactos/REQ-01]]
**Salidas:**
- [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes]]
- [[03-Diseño/01-Ingenieria_Arquitectura/02-STD-05_Flujo_Sistema]]
- [[03-Diseño/01-Ingenieria_Arquitectura/03-STD-06_Modelo_Datos]]
- [[03-Diseño/01-Ingenieria_Arquitectura/04-STD-07_Arquitectura_Python]]
**Notación:** Mermaid.js (Diagramas), Wikilinks (Trazabilidad), Markdown.

#### Herramientas de Verificación y Validación (Calidad)
Para cumplir con el aseguramiento de la calidad, cada artefacto generado en el proceso debe ser validado antes de su aprobación final:

| Artefacto Generado | Herramienta de Validación | Registro de Calidad |
| :--- | :--- | :--- |
| Diagrama de Componentes | Inspección de Paridad Código-Diseño | [[03-Diseño/02-Calidad_Revisiones/HALLAZGO-01_Inconsistencia_Tecnologica]] |
| Flujo del Sistema | Walkthrough de Petición HTTP | [[03-Diseño/02-Calidad_Revisiones/CL-03_Checklist_Diseño]] |

---

## Proceso

### T-01: Mapeo de Componentes de Hardware y Software
1. **Inspección de Directorios**: Acceder al repositorio local y listar las carpetas para identificar capas (ej. `static/`, `templates/`, `services/`).
2. **Análisis de Stack**: Revisar el archivo `app.py` y `requirements.txt` para confirmar versiones de Python, Flask y OpenCV.
3. **Modelado Visual**: Crear un diagrama de bloques que separe el Cliente (Navegador) del Servidor (Flask) y las herramientas auxiliares.
4. **Documentación**: Registrar los resultados en el archivo de salida con sus respectivas tablas de tecnologías.
- **Salida**: [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes]]

### T-02: Modelado de Flujo de Datos (LifeCycle)
1. **Rastreo de Ruta**: Identificar un endpoint crítico (ej. `@app.route('/upload')`) en el código.
2. **Mapeo de Funciones**: Seguir la llamada desde el `POST` del frontend hasta la función de procesamiento en el backend.
3. **Diagramación**: Traducir el rastreo a un diagrama de secuencia **Mermaid.js** mostrando la interacción entre Usuario, Servidor Flask y Módulos de Visión.
4. **Validación de Pasos**: Explicar qué ocurre con los datos en cada salto del diagrama.
- **Salida**: [[03-Diseño/01-Ingenieria_Arquitectura/02-STD-05_Flujo_Sistema]]

### T-03: Ingeniería Inversa de Datos
1. **Mapeo de Estructuras**: Localizar en el código las clases o diccionarios que almacenan la información de los marcos (ej. `marcos_list`).
2. **Definición de Atributos**: Extraer los nombres de las variables reales (ej. `width_px`, `texture_id`) y asignarles una descripción funcional según el negocio.
3. **Relacionamiento**: Identificar cómo se vincula una imagen subida por el usuario con el catálogo de marcos seleccionado.
4. **Creación de Tabla**: Documentar la entidad "Marco" y su esquema de datos técnico.
- **Salida**: [[03-Diseño/01-Ingenieria_Arquitectura/03-STD-06_Modelo_Datos]]

### T-04: Documentación de la Arquitectura de Implementación
1. **Inventario de Módulos**: Listar todos los archivos `.py` y sus funciones principales.
2. **Análisis de Responsabilidad**: Describir qué hace cada módulo (ej. `vision.py` -> Detección de bordes).
3. **Mapeo de Dependencias**: Documentar qué librerías externas (OpenCV, Pillow) utiliza cada módulo y para qué proceso específico.
4. **Diagramación de Paquetes**: Crear un diagrama que muestre cómo se importan los módulos entre sí.
- **Salida**: [[03-Diseño/01-Ingenieria_Arquitectura/04-STD-07_Arquitectura_Python]]

---

## Referencias
- **SWEBOK v4**: Knowledge Area 2 - Software Design.
- **Daniel Galin (2004)**: Software Quality Assurance - "Infrastructure for Error Prevention".
- **Modelo ETVX**: Entry, Task, Validation, Exit (IBM Standard).
- **Directiva del Profesor**: "Si el artefacto sale mal, cambia el proceso" (Revisión 2026-05-14).
