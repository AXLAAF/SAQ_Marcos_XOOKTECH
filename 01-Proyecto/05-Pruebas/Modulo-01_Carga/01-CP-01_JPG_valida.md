---
id: CP-01
titulo: Carga de imagen JPG valida
modulo: Carga
tipo_prueba: Sistema
requerimiento: REQ-01_Carga_Imagen
version_sistema: "1.0"
estado: Pendiente
entrada: Archivo JPG de 2MB
precondiciones: Sistema iniciado, pagina de carga visible
pasos:
  - 1. Hacer click en boton "Subir imagen"
  - 2. Seleccionar archivo JPG valido
  - 3. Confirmar seleccion
resultado_esperado: La imagen se carga correctamente y aparece en el canvas de previsualizacion
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

# CP-01: Carga de imagen JPG valida

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-01 |
| **Modulo** | Carga (Modulo-01) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el sistema permite cargar correctamente una imagen en formato JPG valida.

## 3. Datos de Prueba

| Campo | Valor |
|-------|-------|
| Archivo de entrada | `test_foto_cliente.jpg` |
| Tamano | 2 MB |
| Formato | JPG |
| Resolucion | 1920x1080 |

## 4. Pasos de Ejecucion

1. Acceder a la pagina principal del sistema
2. Localizar el boton "Subir imagen" o area de arrastre
3. Hacer click en el boton o arrastrar el archivo
4. Seleccionar el archivo `test_foto_cliente.jpg`
5. Confirmar la seleccion

## 5. Resultado Esperado

- La imagen se muestra en el canvas de previsualizacion
- No se muestra mensaje de error
- El indicador de carga desaparece
- La imagen mantiene su calidad original

## 6. Criterios de Exito

- [ ] La imagen se carga exitosamente
- [ ] No se muestran errores en consola
- [ ] La imagen es visible en el canvas

## 7. Trazabilidad

- Requerimiento: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*