---
id: CP-XX
titulo: "[Titulo de la Prueba]"
modulo: "[Carga/Catalogo/Previsualizacion]"
tipo_prueba: "[Caja Negra / Funcional / Regresion]"
requerimiento: [[REQ-XX]]
estado: Pendiente
prioridad: [Alta/Media/Baja]
responsable: Axel Morales
---

# CP-XX: [Titulo de la Prueba]

## 1. Descripcion de la Prueba
[Que se intenta verificar. Ej: Validar que el sistema rechaza archivos .exe]

## 2. Precondiciones
- [ ] El sistema esta en la pantalla de carga.
- [ ] No hay ninguna imagen cargada previamente.

## 3. Datos de Entrada (Inputs)
- **Archivo**: `test_file.exe`
- **Tamaño**: 1 MB

## 4. Procedimiento de Ejecucion (Pasos)
1. Presionar el boton "Subir foto".
2. Seleccionar el archivo `test_file.exe` desde el explorador.
3. Observar la respuesta del sistema.

## 5. Resultados Esperados
- El sistema NO permite la carga.
- Se muestra un mensaje de error: "Formato no valido. Solo JPG/PNG".

## 6. Resultados Reales (Evidencia)
- **Estado**: [POR EJECUTAR]
- **Fecha de Ejecucion**: 
- **Resultado**: [PENDIENTE]
- **Observaciones**: 

## 7. Trazabilidad
- Requerimiento: [[REQ-XX]]
- Defecto Asociado: [[DEF-XX]] (si aplica)
- Change Request: [[CR-XX]] (si aplica)
