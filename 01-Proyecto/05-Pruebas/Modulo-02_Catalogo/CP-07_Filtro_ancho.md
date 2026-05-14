---
id: CP-07
titulo: Filtro por ancho de marco
modulo: Catalogo
tipo_prueba: Sistema
requerimiento: REQ-05_Filtrado_Catalogo
version_sistema: "1.0"
estado: Pendiente
entrada: Rango de ancho 30-50 cm
precondiciones: Catalogo cargado completamente
pasos:
  - 1. Acceder a la seccion Catalogo
  - 2. Ingresar rango de ancho: 30-50 cm
  - 3. Observar resultados filtrados
resultado_esperado: Solo se muestran marcos con ancho entre 30 y 50 cm
resultado_actual: ""
paso_fallo: ""
severidad_defecto: ""
fecha_ejecucion: ""
responsable: ""
tags:
  - cp/pendiente
  - modulo/catalogo
  - req/funcional
---

# CP-07: Filtro por ancho de marco

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-07 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-05_Filtrado_Catalogo]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el filtro por rango de ancho muestra solo los marcos cuyas dimensiones estan dentro del rango especificado.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Filtro seleccionado | Ancho: 30-50 cm |
| Valor esperado | Marcos con 30cm <= ancho <= 50cm |

## 4. Pasos de Ejecucion

1. Acceder al catalogo
2. Localizar campo de filtro de ancho
3. Ingresar valor minimo: 30
4. Ingresar valor maximo: 50
5. Observar resultados

## 5. Resultado Esperado

- Se muestran solo marcos con ancho entre 30 y 50 cm
- El contador de resultados se actualiza
- La seleccion es inclusiva (incluye valores limite)

## 6. Criterios de Exito

- [ ] Filtro incluye marcos de 30cm
- [ ] Filtro incluye marcos de 50cm
- [ ] Excluye marcos menores a 30cm y mayores a 50cm

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-05_Filtrado_Catalogo]] - RN-05-03
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*