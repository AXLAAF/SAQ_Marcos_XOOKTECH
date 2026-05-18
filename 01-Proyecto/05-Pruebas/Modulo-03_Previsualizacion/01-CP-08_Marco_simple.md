# CP-08: Previsualizacion de marco simple

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-08 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-02_Previsualizacion_Marco]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-03_Generacion_Marcos_3D]] |
| **Estado** | Pendiente |

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

- Requerimientos: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-02_Previsualizacion_Marco]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-03_Generacion_Marcos_3D]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01-Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*
