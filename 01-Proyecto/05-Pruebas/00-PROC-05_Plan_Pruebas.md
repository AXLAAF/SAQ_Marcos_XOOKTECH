# Proceso 5 — Plan de Pruebas (Ciclo PDCA)
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

> **Fundamentación**: Siguiendo a Lewis (2004), el aseguramiento de la calidad mediante pruebas requiere un enfoque sistemático **PDCA**. Para el Visualizador de Marcos, las pruebas se centran en la precisión de los algoritmos de **OpenCV** para la detección de dimensiones y la fidelidad del renderizado con **Pillow**.

## 1. Estructura del Proceso (Modelo ETVX)

| Fase | Definición | Detalles |
| :--- | :--- | :--- |
| **[E] Entry** | Criterios de Entrada | Arquitectura Flask/OpenCV validada + Repositorio sincronizado. |
| **[T] Tasks** | Tareas Operativas | Diseñar casos de prueba técnicos (API y Procesamiento de Imagen). |
| **[V] Verification** | Calidad de Pruebas | El Líder SQA valida que los CPs cubran los casos de borde técnicos. |
| **[X] Exit** | Criterios de Salida | Cobertura de REQs > 95% y evidencia de pruebas en el prototipo. |

## 2. Metodología de Pruebas Técnicas

### 2.1 Pruebas de Integración (Flask API)
Se deben verificar las rutas del servidor Flask:
- `/upload`: Validación de seguridad y tipos MIME (JPG/PNG).
- `/process`: Tiempo de respuesta del motor OpenCV.
- `/render`: Consumo de memoria al procesar imágenes de alta resolución.

### 2.2 Pruebas de Algoritmos (OpenCV / Pillow)
- **Precisión:** Verificar que la "Detección de Ancho" tenga un margen de error < 5%.
- **Fidelidad:** Validar que la superposición de texturas (Pillow) no pierda la proporción original de la imagen del usuario.

## 3. Matriz de Casos de Prueba (Priorizada)

| ID | Título | Tecnología | Requerimiento |
| :--- | :--- | :--- | :--- |
| **CP-01** | Carga de Imagen Válida | Flask/Security | REQ-01 |
| **CP-02** | Detección de Contornos | OpenCV | REQ-02 |
| **CP-03** | Renderizado de Marco 3D | Pillow | REQ-03 |
| **CP-04** | Filtrado Dinámico | Flask/Logic | REQ-05 |

## 4. Mejora Continua (Action)

Si un caso de prueba falla debido a un error de lógica en el procesamiento de imagen, el **Analista Técnico** debe documentarlo en el [[07-Control/02-REG-03_Registro_Defectos]] y coordinar con el **Líder SQA** la actualización de los estándares de codificación para evitar recurrencias.

---
*Actualización conforme a los estándares técnicos del proyecto: 2026-05-14*