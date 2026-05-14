---
id: CP-03
titulo: Manejo de imagen muy grande
modulo: Carga
tipo_prueba: Sistema
requerimiento: REQ-01_Carga_Imagen
version_sistema: "1.0"
estado: Pendiente
entrada: Archivo JPG de 25MB (tamano excesivo)
precondiciones: Sistema iniciado, pagina de carga visible
pasos:
  - 1. Hacer click en boton "Subir imagen"
  - 2. Seleccionar archivo JPG de 25MB
  - 3. Confirmar seleccion
resultado_esperado: El sistema comprime la imagen o muestra mensaje de tamano excesivo
resultado_actual: ""
paso_fallo: ""
severidad_defecto: ""
fecha_ejecucion: ""
responsable: ""
tags:
  - cp/pendiente
  - modulo/carga
  - req/funcional
---

# CP-03: Manejo de imagen muy grande

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-03 |
| **Modulo** | Carga (Modulo-01) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el sistema maneja adecuadamente imagenes que exceden el tamano maximo permitido (10MB).

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Archivo de entrada | `foto_grande.jpg` |
| Tamano | 25 MB |
| Formato | JPG |

## 4. Pasos de Ejecucion

1. Acceder a la pagina principal del sistema
2. Hacer click en el boton "Subir imagen"
3. Seleccionar un archivo JPG de 25MB
4. Confirmar la seleccion

## 5. Resultado Esperado (Opcion 1 - Compresion)

- El sistema comprime automaticamente la imagen
- Se muestra indicador de procesamiento
- La imagen se carga exitosamente
- No se degrada visiblemente la calidad

**Resultado Esperado (Opcion 2 - Rechazo)**

- Se muestra mensaje: "El archivo excede el tamano maximo de 10MB"
- Se sugiere comprimir la imagen

## 6. Criterios de Exito

- [ ] El sistema maneja el archivo grande sin bloquearse
- [ ] Se proporciona retroalimentacion al usuario
- [ ] El resultado es util (imagen cargada o mensaje claro)

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]] - Criterio de aceptacion CA-03
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*