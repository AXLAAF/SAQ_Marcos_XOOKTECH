# CP-08: Previsualizacion de marco simple
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo              | Valor                                                                                  |                                                                                                                       |                               |
| ------------------ | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| **ID**             | CP-08                                                                                  |                                                                                                                       |                               |
| **Modulo**         | Previsualizacion (Modulo-03)                                                           |                                                                                                                       |                               |
| **Tipo de Prueba** | Sistema                                                                                |                                                                                                                       |                               |
| **Requerimiento**  | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco | REQ-02 Previsualización Marco]], [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/06-REQ-03_Generacion_Marcos_3D | REQ-03 Generación Marcos 3D]] |
| **Estado**         | Pendiente                                                                              |                                                                                                                       |                               |

## 2. Descripcion

Verificar que la previsualizacion 3D renderiza correctamente un marco simple sobre la foto del cliente.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Imagen de entrada | foto_cliente.jpg |
| Marco seleccionado | Marco simple (no doble) |
| Renderizado esperado | Three.js/WebGL |

## 4. Pasos de Ejecucion

1. Cargar una foto de prueba en el sistema
2. Navegar al catalogo de marcos
3. Seleccionar un marco simple
4. Observar el renderizado de previsualizacion

## 5. Resultado Esperado

- El marco se rendered alrededor de la foto
- La perspectiva 3D es correcta
- La textura del marco se aplica adecuadamente
- El tiempo de renderizado es < 2 segundos

## 6. Criterios de Exito

- [ ] Marco visible en los 4 lados
- [ ] Textura aplicada correctamente
- [ ] Sin errores de WebGL
- [ ] Rendimiento aceptable

## 7. Trazabilidad

- Requerimientos: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02 Previsualización Marco]], [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/06-REQ-03_Generacion_Marcos_3D|REQ-03 Generación Marcos 3D]]
- Plan Maestro: [[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*