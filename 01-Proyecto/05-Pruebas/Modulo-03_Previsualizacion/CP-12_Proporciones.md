---
id: CP-12
titulo: Proporcion correcta de marco con foto
modulo: Previsualizacion
tipo_prueba: Sistema
requerimiento: REQ-02_Previsualizacion_Marco
version_sistema: "1.0"
estado: Pendiente
entrada: Foto con diferentes proporciones + marco
precondiciones: Previsualizacion activa
pasos:
  - 1. Cargar foto cuadrada (1:1)
  - 2. Seleccionar marco 20x30cm
  - 3. Observar proporcion
  - 4. Repetir con foto panoramica (16:9)
resultado_ellesperado: El marco mantiene proporcion correcta independientemente del tamano de la foto
resultado_actual: ""
paso_fallo: ""
severidad_defecto: ""
fecha_ejecucion: ""
responsable: ""
tags:
  - cp/pendiente
  - modulo/previsualizacion
  - req/funcional
---

# CP-12: Proporcion correcta de marco con foto

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-12 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-02_Previsualizacion_Marco]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que las proporciones del marco se mantienen correctas independientemente del tamano y proporcion de la foto del cliente.

## 3. Datos de Prueba

| Prueba | Tamano de foto | Proporcion |
|--------|---------------|------------|
| 1 | 1000x1000 px | 1:1 (cuadrada) |
| 2 | 1920x1080 px | 16:9 (panoramica) |
| 3 | 800x600 px | 4:3 (estandar) |

## 4. Pasos de Ejecucion

1. Cargar foto cuadrada (1:1)
2. Seleccionar marco 20x30cm
3. Observar la previsualizacion
4. Repetir con otras proporciones
5. Verificar que no haya deformacion

## 5. Resultado Esperado

- El marco mantiene sus proporciones (20x30cm)
- La foto se ajusta dentro del marco
- No hay deformacion de la imagen
- El resultado es visualmente correcto

## 6. Criterios de Exito

- [ ] Marco sin deformacion
- [ ] Foto centrada correctamente
- [ ] Funciona con todas las proporciones

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-02_Previsualizacion_Marco]] - CA-02
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*