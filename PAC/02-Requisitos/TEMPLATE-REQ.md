---
id: REQ-XXX
titulo: [Titulo del requerimiento]
version: "1.0"
estado: Pendiente # Pendiente | Revisado | Aprobado | Rechazado
prioridad: Media # Alta | Media | Baja
tipo: Funcional # Funcional | No_Funcional | Regla_Negocio
modulo: [Carga | Catalogo | Previsualizacion | Pantalla_Secundaria | General]
fecha_creacion: YYYY-MM-DD
ultima_revision: YYYY-MM-DD
responsable: [Nombre]
solicitado_por: [Cliente o integrante]
objetivo_negocio: [Valor que aporta al cliente o al negocio]
fuente:
  - Proyecto/01-Linea_Base/03-Acuerdos_Cliente.md
dependencias:
  - [REQ-YYY_Nombre]
change_requests:
  - [CR-XX_Nombre]
casos_prueba:
  - [CP-XX_Nombre]
validacion_evidencia: [Ruta a correo, captura o minuta aprobada]
resultado_verificacion: Pendiente # Pendiente | Aprobado | Requiere_Retrabajo
porcentaje_verificacion: 0
revisor_verificacion: [Nombre]
fecha_verificacion: YYYY-MM-DD
---

# REQ-XXX - [Titulo del requerimiento]

> Proceso relacionado: `PAC/02-Requisitos/PROC-02_Especificacion_Requerimientos.md`

## 1. Descripcion General

[Describa la necesidad desde la perspectiva del usuario o negocio. Indique que problema resuelve y que resultado espera el cliente.]

## 2. Alcance del Requerimiento

- **Incluye:** [Funciones, datos, pantallas o reglas incluidas]
- **No incluye:** [Limites del requerimiento para evitar ambiguedad]

## 3. Reglas de Negocio

- `RN-XXX-01`: [Regla cuantificable]
- `RN-XXX-02`: [Regla cuantificable]
- `RN-XXX-03`: [Condicion, limite o politica aplicable]

## 4. Precondiciones

- [Condicion del sistema, del usuario o de datos requerida antes de ejecutar el flujo]
- [Dependencia previa si aplica]

## 5. Flujo Principal

1. [Actor ejecuta la accion inicial]
2. [El sistema procesa o valida]
3. [El sistema responde con un resultado observable]
4. [Condicion de cierre exitosa]

## 6. Flujos Alternativos y de Excepcion

| ID | Tipo | Condicion | Respuesta esperada |
| :-- | :-- | :-- | :-- |
| FA-01 | Alternativo | [Condicion valida distinta al flujo principal] | [Respuesta del sistema] |
| FE-01 | Excepcion | [Error, dato invalido o indisponibilidad] | [Respuesta controlada del sistema] |

## 7. Criterios de Aceptacion (BDD)

| CA-ID | Dado | Cuando | Entonces |
| :-- | :-- | :-- | :-- |
| CA-01 | [Contexto] | [Accion] | [Resultado medible] |
| CA-02 | [Contexto] | [Accion] | [Resultado medible] |

## 8. Restricciones Tecnicas y de Calidad

- [Formato, rendimiento, compatibilidad, limite de datos o dependencia tecnica]
- [Regla de interfaz, seguridad o disponibilidad si aplica]

## 9. Trazabilidad

| Elemento | Referencia |
| :-- | :-- |
| Fuente | [Documento, minuta, acuerdo o `CR`] |
| Change Request asociado | [CR-XX_Nombre o N/A] |
| Caso(s) de prueba | [CP-XX_Nombre] |
| Artefacto de diseno | [Documento de diseno relacionado] |

## 10. Verificacion y Validacion

| Campo | Valor |
| :-- | :-- |
| Checklist aplicado | `PAC/02-Requisitos/CL-02_Verificacion_Requerimientos.md` |
| Resultado de verificacion | [Aprobado / Requiere_Retrabajo] |
| Porcentaje de cumplimiento | [0-100] |
| Revisor | [Nombre] |
| Fecha de verificacion | [YYYY-MM-DD] |
| Validado por | [Cliente / representante] |
| Evidencia de validacion | [Ruta o referencia] |

## 11. Observaciones

- [Supuestos, dudas resueltas, riesgos o acuerdos adicionales]

## 12. Historial de Cambios

| Version | Fecha | Autor | Descripcion |
| :-- | :-- | :-- | :-- |
| 1.0 | YYYY-MM-DD | [Nombre] | Creacion inicial |
