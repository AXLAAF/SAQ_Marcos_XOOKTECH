

**Proceso relacionado:** [[00-PROC-04_Codificacion]]
**Instrucciones generales:** Siga estas reglas para cualquier lenguaje utilizado en el equipo (JS, PHP, React, Kotlin).

## 1. Convenciones de Nombres
**Responsable:** Líder de Desarrollo e Implementación
**Entradas:** Diseño del Sistema y Estándar de Codificación
**Salidas:** Módulos de Código Fuente Verificados
- **Variables y Funciones:** Utilice `camelCase` (ejemplo: `obtenerDatosUsuario`).
- **Clases:** Utilice `PascalCase` (ejemplo: `ProcesadorPagos`).
- **Constantes:** Utilice `SCREAMING_SNAKE_CASE` (ejemplo: `LIMITE_INTENTOS`).

## 2. Claridad y Explicitación
- **Nombres Largos vs Cortos:** Prefiera nombres largos y descriptivos sobre nombres cortos y ambiguos. 
  - Mal: `usr`, `f`.
  - Bien: `usuarioActivo`, `fechaVencimiento`.
- **Sin Acotamientos:** No abrevie palabras a menos que sea un estándar universal (ej. `id`).
- **Funciones Autodescriptivas:** El nombre de la función debe ser un verbo que describa la acción principal.

## 3. Idioma
- Todo el código (nombres de símbolos) y los comentarios técnicos deben estar en **Español**.

## 4. Estructura de Archivos
- Cada archivo debe comenzar con un encabezado simple:
  ```javascript
  /* 
   * Archivo: [nombreArchivo]
   * Tarea: [TAR-YYYY-NNN]
   * Responsable: [Nombre]
   * Descripción: [Qué hace este archivo]
   */
  ```

## 5. Prácticas Recomendadas
- **Rendimiento y Memoria:**
  - Realice un recorrido manual del código enfocado en la lógica de los bucles para evitar iteraciones innecesarias o condiciones de salida infinitas.
  - En lenguajes como Kotlin o PHP, asegúrese de liberar o cerrar recursos (archivos, conexiones a BD) que no se utilicen más.
  - Evite la creación de objetos pesados dentro de bucles si pueden inicializarse fuera.
- Mantenga las funciones pequeñas (idealmente una sola responsabilidad).
- Evite "Magic Numbers"; use constantes definidas.
- Todo código nuevo debe ser revisado por otro integrante antes de ir a la rama principal.