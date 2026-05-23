# CP-12: Proporcion correcta de marco con foto
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-12 |
| **Modulo** | Previsualizacion (Modulo-03) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02 Previsualización Marco]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02 Previsualización Marco]] - CA-02
- Plan Maestro: [[05-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*