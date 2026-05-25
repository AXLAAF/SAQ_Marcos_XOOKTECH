# [PLT-FOR_Estandar_Codificacion] Estándar de Codificación

## Metadatos del Documento
| Campo | Valor |
|---|---|
| Proyecto | |
| Proceso | Codificación (PROC-04) |
| Responsable | Líder de Desarrollo e Implementación |
| Estándar de referencia | ISO/IEC 25010 / SWEBOK v4 Cap. 3 |

---

## 1. Convenciones de Nombres
*   **Variables y Funciones:** Utilizar obligatoriamente `camelCase` (ejemplo: `calcularZoomFotografia`).
*   **Clases y Módulos:** Utilizar obligatoriamente `PascalCase` (ejemplo: `ControladorCatalogo`).
*   **Constantes:** Utilizar `SCREAMING_SNAKE_CASE` (ejemplo: `LIMITE_CARGA_MB`).
*   **Archivos:** Nombres explicativos separados por guion bajo `_` o `camelCase` según la convención del marco de trabajo (framework) utilizado.

---

## 2. Claridad, Nombres y Idioma
*   **Explicitación:** Se prohíbe el uso de acotamientos o abreviaturas que oscurezcan el propósito (ej: usar `usr` en lugar de `usuarioActivo` es una no conformidad).
*   **Funciones Autodescriptivas:** El nombre de la función debe comenzar con un verbo imperativo en español (ej: `obtenerRutaImagen`).
*   **Idioma Único:** Todos los comentarios de código, nombres de variables, funciones, clases y bases de datos deben escribirse en **Español**.

---

## 3. Encabezado Obligatorio de Archivos
Cada archivo de código fuente debe iniciar exactamente con el siguiente bloque de metadatos en comentarios:
```javascript
/* 
 * Archivo: [nombreArchivo]
 * Tarea: [TAR-YYYY-NNN]
 * Responsable: [Nombre del Desarrollador]
 * Descripción: [Breve explicación de la responsabilidad de este archivo]
 */
```

---

## 4. Prácticas de Rendimiento y Mantenibilidad
*   **Lógica de Bucles:** Se debe realizar un recorrido manual exhaustivo de condiciones de salida y bucles para mitigar loops infinitos.
*   **Liberación de Recursos:** Todo archivo, base de datos o socket abierto debe cerrarse explícitamente al finalizar la subrutina.
*   **Desacoplamiento Arquitectónico (Modelo-Vista-Controlador):** Toda consulta SQL o procesamiento de persistencia de base de datos debe residir exclusivamente en las clases de Modelos o Repositorios, nunca en los Controladores o Vistas.

---

## 5. Historial de Cambios
| Versión | Fecha | Autor | Cambio |
|---|---|---|---|
| 1.0 | 2026-05-24 | Líder de Desarrollo | Creación inicial de la plantilla. |
