---
id: CP-04
titulo: Carga completa del catalogo de marcos
modulo: Catalogo
tipo_prueba: Sistema
requerimiento: REQ-04_Catalogo_Marcos
version_sistema: "1.0"
estado: Pendiente
entrada: Ninguna (carga inicial)
precondiciones: Sistema iniciado, conexion a base de datos disponible
pasos:
  - 1. Acceder a la seccion Catalogo
  - 2. Esperar carga de datos
  - 3. Verificar visualizacion del grid
resultado_esperado: El catalogo carga todos los marcos disponibles (~1079)
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

# CP-04: Carga completa del catalogo de marcos

## 1. Informacion del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-04 |
| **Modulo** | Catalogo (Modulo-02) |
| **Tipo de Prueba** | Sistema |
| **Requerimiento** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-04_Catalogo_Marcos]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-06_Datos_Catalogo]] |
| **Estado** | Pendiente |

## 2. Descripcion

Verificar que el catalogo de marcos se carga completamente y muestra todos los registros disponibles en la base de datos.

## 3. Criterios de Aceptacion

- CA-04-01: El sistema muestra el catalogo al iniciar
- CA-04-02: Se cargan todos los marcos disponibles

## 4. Pasos de Ejecucion

1. Abrir la aplicacion web
2. Navegar a la seccion "Catalogo"
3. Observar la carga del catalogo
4. Contar el numero de marcos mostrados

## 5. Resultado Esperado

- Se cargan aproximadamente 1,079 marcos
- El grid de marcos se visualiza correctamente
- Cada marco muestra: imagen, nombre, precio
- El tiempo de carga es aceptable (< 5 segundos)

## 6. Criterios de Exito

- [ ] El catalogo carga todos los marcos
- [ ] No hay errores de conexion
- [ ] La interfaz es responsive

## 7. Trazabilidad

- Requerimientos: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-04_Catalogo_Marcos]], [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-06_Datos_Catalogo]]
- Plan Maestro: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]]

---

*Caso de prueba creado: 2026-03-23*