# CP-03: Manejo de imagen muy grande
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-03 |
| **Modulo** | Carga (Modulo-01) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01 Carga de Imagen]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01 Carga de Imagen]] - Criterio de aceptacion CA-03
- Plan Maestro: [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*