# CP-02: Rechazo de archivo invalido
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-02 |
| **Modulo** | Carga (Modulo-01) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01 Carga de Imagen]] |
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

- Requerimiento: [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01 Carga de Imagen]] - Regla de negocio RN-01-03
- Plan Maestro: [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]

---

*Caso de prueba creado: 2026-03-23*