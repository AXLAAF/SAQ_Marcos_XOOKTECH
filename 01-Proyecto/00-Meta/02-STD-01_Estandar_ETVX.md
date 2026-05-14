---
id: META-04
titulo: Estandar de Estructura de Procesos (Manual de Instrucciones)
version: "4.0"
estado: Activo
tipo: Estandar
fecha_creacion: 2026-05-08
ultima_revision: 2026-05-12
responsable: Axel Morales
referencias_biblio:
  - "Modelo ETVX (IBM)"
  - "SWEBOK v4 KA8"
tags:
  - meta/estandar
  - procesos
  - etvx
  - instrucciones
---

# Instrucciones para la Estructuracion de Procesos (SGC)

> **Directiva de Calidad**: Todo procedimiento operativo (`00-PROC-XX`) debe ser construido bajo el modelo **ETVX**. El incumplimiento de la profundidad tecnica en los campos detallados a continuacion sera motivo de rechazo en la revision interna.

---

## 1. Instrucciones para el Frontmatter YAML (Configuracion)
El encabezado debe ser una declaracion precisa del estado de la fase. Queda prohibido el uso de terminos ambiguos.

1.  **id**: Use el formato `PROC-[Numero de Carpeta]`.
2.  **responsable**: Indique el nombre completo del encargado segun el [[01-Plan_Accion]].
3.  **disparador**: Defina el evento exacto que activa la fase (ej: "Recepcion de Acta de Inicio firmada" o "Cierre de la inspeccion INS-02").
4.  **criterio_entrada (Entry)**: Liste los requisitos minimos para iniciar. No use "documentacion lista"; use "Documento REQ-XX en estado #estado/verificado".
5.  **criterio_salida (Exit)**: Defina la condicion de exito comprobable (ej: "100% de los casos de prueba ejecutados y registrados en CTRL-01").
6.  **entradas y salidas**: Incluya enlaces funcionales `[[Carpeta/Archivo]]`. Toda salida de un proceso DEBE ser entrada de otro.

## 2. Instrucciones para el Cuerpo del Documento

### 2.1 Definicion Operativa
- Redacte el alcance de la fase especificando su posicion en el ciclo PDCA (Plan, Do, Check, Act).
- Instruccion: Indique explicitamente que marco teorico (Lewis, Galin u O'Regan) sustenta las actividades de esta carpeta.

### 2.2 Tareas (Task) - Matriz de Entradas y Salidas
Siga estas directivas de redaccion:

- **Entrada**: Documento especifico del Vault.
- **Actividad (Task)**: Inicie con un verbo de accion tecnica (Analizar, Modelar, Codificar, Inspeccionar). Debe mencionar la herramienta o tecnica usada (ej: "Deteccion de bordes mediante libreria OpenCV" o "Revision formal siguiendo la Checklist CL-02").
- **Salida**: El artefacto resultante con su nombre oficial y prefijo.

*Ejemplo task*

| Entrada (Input) | Actividad (Task) | Salida (Output) |
| :--- | :--- | :--- |
| `[[02-Requisitos/REQ-03]]` | Modelado de la logica 3D usando transformaciones afines en Python | `[[03-Diseño/DIS-01]]` |

### 2.3 Verificacion (Validation)
Para evitar "huecos" de calidad, esta seccion debe ser prescriptiva:
1.  **Checklist Asociada**: Vincule obligatoriamente la `[[00-Meta/99-Plantillas_y_Checklists/CL-XX]]` que valida las salidas de esta fase.
2.  **Metricas de Proceso**: Defina un indicador numerico real (ej: "Densidad de defectos = Errores encontrados / KLOC" o "% de Requerimientos con Trazabilidad completa").

## 3. Directiva de Trazabilidad
- Es obligatorio que el Auditor (Axel) valide que los enlaces entre REQ, DIS, COD y CP sean bidireccionales y funcionales antes de marcar el proceso como `#estado/verificado`.

---
*Ultima actualizacion: 2026-05-12 | Axel Morales (SQA chambador)*
