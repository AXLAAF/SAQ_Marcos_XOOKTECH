# CP-02: Rechazo de archivo invalido

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-02 |
| **Modulo** | Carga (Modulo-01) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el sistema rechaza archivos con formatos no validos y muestra un mensaje apropiado.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Archivo de entrada | `documento.pdf` |
| Formato | PDF (no valido) |

## 4. Pasos de Ejecucion

1. Acceder a la pagina principal del sistema
2. Hacer click en el boton "Subir imagen"
3. Seleccionar un archivo PDF
4. Confirmar la seleccion

## 5. Resultado Esperado

- Se muestra mensaje de error: "Formato de archivo no valido. Solo se aceptan JPG, PNG, WebP"
- No se carga ningun archivo
- El sistema permanece en estado funcional

## 6. Criterios de Exito

- [ ] El sistema rechaza el archivo PDF
- [ ] Se muestra mensaje de error claro
- [ ] El sistema no se bloquea

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]] - Regla de negocio RN-01-03
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01-Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*
