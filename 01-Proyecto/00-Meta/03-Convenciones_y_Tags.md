---
id: META-02
titulo: Convenciones y Tags del Vault (Manual de Instrucciones Profundo)
version: "3.0"
estado: Activo
tipo: Estandar
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-12
responsable: Axel Morales
referencias_biblio:
  - "Daniel Galin - SQA Components (Infraestructura)"
  - "SWEBOK v4 - Configuration Management"
tags:
  - meta/estandar
  - gobernanza
  - instrucciones
  - trazabilidad
---

# Manual de Convenciones y Tags del SGC (Rigor Tecnico)

> **Directiva de Infraestructura**: El cumplimiento de estas convenciones es la base de la Administracion de la Configuracion (SCM). Ningun documento sera aceptado en Linea Base sin cumplir con el escorado numerico y el sistema de tags detallado.

---

## 1. Directiva de Jerarquia Numerica y Escorado
Para garantizar la navegacion logica y la revision
:
1.  **Carpetas (00-09)**: Representan el Ciclo de Vida del Software. Queda prohibido alterar el orden numerico de las fases definido en el [[00-Meta/00-Indice_Procesos]].
2.  **Archivos de Proceso (00-PROC)**: Todo directorio de fase DEBE iniciar con el archivo `00-PROC-XX_Nombre.md`. Este archivo es la autoridad normativa de la carpeta.
3.  **Archivos de Artefacto (Secuenciales)**: Numerar del `01` al `90` segun su relevancia o secuencia de produccion. El numero `99` se reserva exclusivamente para plantillas y checklists locales.

## 2. Instrucciones de Nomenclatura (Prefijos Tecnicos)
El nombre del archivo debe reflejar su naturaleza para facilitar la Trazabilidad Automatizada:

| Prefijo | Significado Tecnico | Aplicacion Obligatoria |
| :--- | :--- | :--- |
| **PROC-** | Procedimiento Operativo (ETVX) | El manual de instrucciones de la carpeta. |
| **REQ-** | Requerimiento Funcional/No Funcional | Declaracion de necesidad del sistema. |
| **DIS-** | Documento de Diseño | Especificacion tecnica (Arquitectura, Datos, Flujos). |
| **COD-** | Documentacion de Codigo | Detalle de modulos, clases y funciones reales. |
| **CP-** | Caso de Prueba (Testing) | Guion de validacion con resultados esperados. |
| **MNT-** | Plan de Mantenimiento | Estrategia de soporte y correccion de errores. |
| **CTRL-** | Control y Metricas | Dashboards, registros de defectos y RTM. |
| **DESP-** | Documento de Despliegue | Guia de instalacion y manual de usuario. |
| **INS-** | Reporte de Inspeccion | Resultados de revisiones formales (Galin). |
| **CL-** | Checklist de Verificacion | Filtros de calidad (Pasa/No Pasa). |

## 3. Directiva de Actualizacion de Nomenclatura
En caso de que algun integrante del proyecto requiera el uso de nuevos prefijos o variaciones en la nomenclatura:
- **Procedimiento de Extension**: El miembro del equipo (Samuel o Carlos) debe notificar a **Axel Morales** sobre la necesidad detectada.
- **Accion del Auditor**: Axel integrara el nuevo prefijo en este manual y actualizara los archivos de gobernanza (`00-Meta/00-PROC-00` y `00-Meta/00-Indice_Procesos`) para asegurar que la nueva convencion sea oficial y trazable para todo el equipo.

## 4. Sistema de Etiquetado Dinamico (Tags de Estado)
Es obligatorio que cada nota gestione su ciclo de vida mediante los siguientes tags en el YAML:

1.  `#estado/borrador`: El documento esta en construccion. No es apto para ser entrada de ningun otro proceso.
2.  `#estado/verificado`: El documento ha superado la Checklist (`CL`) de su fase. Puede ser usado como entrada en la fase subsiguiente.
3.  `#estado/aprobado`: El documento forma parte de la **Linea Base Congelada**. Cualquier modificacion requiere un `CR` (Change Request).
4.  `#sqa/evidencia`: Reservado para notas que contienen capturas, logs de error o resultados reales del prototipo (Blindaje Anti-IA).

## 4. Instrucciones de Enlace y Trazabilidad Profunda
1.  **Enlace Wikilink**: Use `[[Carpeta/Nombre_Archivo]]`. Evite el uso de alias si estos ocultan el prefijo tecnico.
2.  **Cadena de Trazabilidad**: Todo archivo `CP` debe tener un enlace directo en el cuerpo a su `REQ`. Todo `COD` debe enlazar a su `DIS` correspondiente.
3.  **Control de Versiones**: Al pasar un archivo de `#estado/borrador` a `#estado/verificado`, se debe incrementar el decimal de la version (v1.0 -> v1.1).

---
*Ultima actualizacion: 2026-05-12 | Axel Morales (SQA Lead)*
