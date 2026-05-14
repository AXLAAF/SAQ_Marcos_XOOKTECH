---
id: REQ-06
titulo: Datos del Catalogo de Marcos
version: "1.0"
estado: Implementado
prioridad: Alta
tipo: Funcional
modulo: Base de Datos
fecha_creacion: 2026-03-19
ultima_revision: 2026-03-19
responsable: Analista Técnico
fuente: Propuesta recuperada, Acuerdos con el cliente
criterios_aceptacion:
  - CA-01: El catalogo incluye la clave de cada marco
  - CA-02: El catalogo incluye las dimensiones (ancho, alto)
  - CA-03: El catalogo incluye la textura del marco
  - CA-04: El catalogo incluye la forma 3D del marco
  - CA-05: El catalogo contiene aproximadamente 1000 marcos
dependencias:
  - REQ-03_Generacion_Marcos_3D
change_requests: []
casos_prueba: []
referencias_biblio:
  - SWEBOK v4 KA1 sec 4.5
tags:
  - req/funcional
  - modulo/base-datos
  - req/implementado
---

# REQ-06: Datos del Catalogo de Marcos

## 1. Descripcion General

El catalogo de marcos debe contener toda la informacion necesaria para que el sistema pueda mostrar y renderizar cada marco. Esto incluye datos alfanumericos, imagenes y modelos 3D.

## 2. Reglas de Negocio

- RN-06-01: Cada marco debe tener una clave unica de identificacion
- RN-06-02: Cada marco debe tener dimensiones de ancho y alto en centimetros
- RN-06-03: Cada marco debe tener una imagen de textura frontal
- RN-06-04: Cada marco debe tener un modelo 3D asociado
- RN-06-05: El catalogo debe contener todos los marcos disponibles (~1000+)

## 3. Precondiciones

- El inventario de marcos de Enmarcame ha sido escaneado
- El programa de procesamiento ha generado los modelos 3D

## 4. Flujo Principal (Happy Path)

1. El equipo de Enmarcame proporciona el inventario de marcos
2. Se escanean las texturas de cada marco (200 por semana)
3. El programa Python procesa las imagenes y genera modelos 3D
4. Los datos se cargan en la base de datos PostgreSQL
5. El sistema queda listo para usar con el catalogo completo

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | Se agrega un nuevo marco al inventario | Se escanea, procesa y agrega al catalogo |
| FA-02 | Se agota un marco del inventario | Se marca como no disponible en el catalogo |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | Error al cargar datos en la base de datos | El sistema registra el error y reintenta |
| FE-02 | Imagen faltante para un marco | Se marca el marco como "pendiente de imagen" |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | Se consultan todos los marcos en la base de datos | Se ejecuta query | Se devuelven todos los campos (clave, dimensiones, textura, 3D) |
| CA-02 | El inventario tiene 1079 marcos | Se cargan en el sistema | Todos los marcos aparecen en el catalogo |
| CA-03 | Se selecciona un marco para previsualizar | Se consulta el marco | El sistema tiene todos los datos necesarios para renderizar |

## 8. Restricciones Tecnicas

- Base de datos: PostgreSQL
- Almacenamiento de imagenes: Sistema de archivos o blob
- Almacenamiento de modelos 3D: Formato GLTF/GLB
- Indexacion: Por clave, categoria, color, ancho

## 9. Dependencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-03_Generacion_Marcos_3D]] - Generacion de modelos 3D

## 10. Trazabilidad

- Casos de Prueba: Pendientes de definir en PROC-05
- Change Requests: No aplica

---

*Requerimiento creado: 2026-03-19 | Ultima actualizacion: 2026-03-19*
*Referencia: [[01-Propuesta_Recuperada]], [[02-Acuerdos_Cliente]]