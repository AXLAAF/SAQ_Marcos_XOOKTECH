---
id: PROC-04
titulo: Proceso 4 - Arquitectura del Sistema
version: "1.0"
estado: Pendiente
tipo: Proceso
fecha_creacion: 2026-03-19
ultima_revision: 2026-03-19
responsable: Axel Morales
disparador: Requerimientos especificados y aprobados
criterio_entrada: Requerimientos profundos completados (PROC-02)
criterio_salida: Documentacion de arquitectura completa
entradas:
  - Requerimientos especificacion profunda
  - Codigo fuente en GitHub
  - Documentacion tecnica existente
salidas:
  - 01-Diagrama_Componentes.md
  - 02-Flujo_Sistema.md
  - 03-Modelo_Datos.md
  - 04-Modulos_Python.md
actividades:
  - Analizar el codigo fuente existente
  - Crear diagrama de componentes
  - Documentar el flujo del sistema
  - Definir el modelo de datos
  - Documentar los modulos Python
  - Identificar integraciones faltantes
roles:
  - Axel Morales (analista tecnico)
  - Samuel Blanco (validacion)
referencias_biblio:
  - "SWEBOK v4 KA2 - Diseno de Software"
  - "SWEBOK v4 KA8 - Ingenieria de Procesos"
  - "Repositorio: https://github.com/Bigsami89/Marcos2"
tags:
  - proceso
  - arquitectura
---

# Proceso 4 — Arquitectura del Sistema

> **Justificacion**: Segun SWEBOK v4 KA2, "el proposito del diseno de software es proporcionar una descripcion de la arquitectura del sistema que sirva como base para la implementacion". La arquitectura documenta como los componentes del sistema interactuan para satisfacer los requerimientos, y es esencial para el mantenimiento y evolucion del sistema.

## 1. Definicion del Proceso

| Campo | Descripcion |
| :-- | :-- |
| **Disparador** | Requerimientos especificacion profunda completados. Necesario porque la arquitectura debe basarse en requerimientos detallados para evitar diseñar componentes que no corresponden al alcance real. (SWEBOK v4 KA2) |
| **Criterio de Entrada** | REQ-01 a REQ-10 con especificacion completa. Se usa para identificar los componentes, flujos y entidades que la arquitectura debe soportar, asegurando trazabilidad REQ → componente. |
| **Actividades** | Ver lista abajo |
| **Salida / Entregable** | Documentos de arquitectura (diagrama componentes, flujo, modelo datos, modulos Python). Proporcionan la vision tecnica necesaria para implementar y mantener el sistema. |
| **Responsable** | Axel Morales (analista tecnico) + Samuel Blanco (validacion) |
| **Criterio de Salida** | Diagramas y documentacion de arquitectura revisados y aprobados. Cada componente debe trazarse a al menos un REQ. |

## 2. Actividades del Proceso

1. Analizar el codigo fuente existente en GitHub.
2. Crear diagrama de componentes del sistema.
3. Documentar el flujo del sistema (desde entrada hasta salida).
4. Definir el modelo de datos (entidades, atributos, relaciones).
5. Documentar los modulos Python y su proposito.
6. Identificar integraciones faltantes o areas de mejora.
7. Validar la arquitectura contra los requerimientos.

## 3. Artefactos de Arquitectura

### 3.1 Diagrama de Componentes

Este documento debe contener:
- Vista general de la arquitectura
- Componentes principales y sus responsabilidades
- Interfaces entre componentes
- tecnologias utilizadas por componente
- Diagrama de despliegue (opcional)

### 3.2 Flujo del Sistema

Este documento debe contener:
- Diagrama de flujo de datos
- Secuencia de operaciones
- Puntos de decision
- Manejo de errores
- Integraciones externas

### 3.3 Modelo de Datos

Este documento debe contener:
- Entidades y sus atributos
- Relaciones entre entidades
- Tipos de datos
- Restricciones
- Diagrama ER (Entity-Relationship)

### 3.4 Modulos Python

Este documento debe contener:
- Lista de modulos Python
- Proposito de cada modulo
- Funciones principales
- Dependencias entre modulos
- Parametros de entrada y salida

## 4. Estructura de la Documentacion

### 4.1 01-Diagrama_Componentes.md

```markdown
# Diagrama de Componentes - Visualizador de Marcos

## 1. Vista General de la Arquitectura
[Descripcion de la arquitectura general del sistema]

## 2. Componentes Principales

### 2.1 Componente: [Nombre]
| Aspecto | Descripcion |
| :-- | :-- |
| Proposito | [Que hace este componente] |
| Responsabilidades | [Lista de responsabilidades] |
| Tecnologias | [Tecnologias utilizadas] |
| Interfaces | [APIs, protocolos] |
| Dependencias | [Otros componentes] |

## 3. Diagrama de Arquitectura
[Insertar diagrama en formato Mermaid]

## 4. Despliegue
[Diagrama de despliegue si aplica]

## 5. Consideraciones de Seguridad
[Aspectos de seguridad de la arquitectura]
```

### 4.2 02-Flujo_Sistema.md

```markdown
# Flujo del Sistema - Visualizador de Marcos

## 1. Flujo Principal

### 1.1 Carga de Imagen
[Descripcion del flujo]

## 2. Flujos Alternativos
[Otros flujos]

## 3. Manejo de Errores
[Como se manejan los errores]

## 4. Diagramas de Secuencia
[Diagramas Mermaid]
```

### 4.3 03-Modelo_Datos.md

```markdown
# Modelo de Datos - Visualizador de Marcos

## 1. Entidades

### 1.1 Entidad: [Nombre]
| Atributo | Tipo | Restricciones |
| :-- | :-- | :-- |
| [Nombre] | [Tipo] | [Restricciones] |

## 2. Relaciones
[Diagrama ER y descripcion]

## 3. Indices
[Indices importantes]
```

### 4.4 04-Modulos_Python.md

```markdown
# Modulos Python - Visualizador de Marcos

## 1. Modulos

### 1.1 modulo_principal.py
| Aspecto | Descripcion |
| :-- | :-- |
| Proposito | [Que hace] |
| Funciones | [Lista] |
| Entrada | [Parametros] |
| Salida | [Retorno] |
```

## 5. Criterios de Aceptacion del Proceso

- [ ] Diagrama de componentes creado y documentado
- [ ] Flujo del sistema documentado
- [ ] Modelo de datos definido
- [ ] Modulos Python documentados
- [ ] Comparacion con requerimientos verificada
- [ ] Proceso cerrado con estado = "Completado"

## 6. Dependencias

- **Pre-requisito**: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/PROC-02_Especificacion_Requerimientos]]
- **Post-requisito**: [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/PROC-05_Plan_Pruebas]]

## 7. Referencias

- [[01-Proceso_Gobernanza_Vault]]
- [[02-Convenciones_y_Tags]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/01-Diagrama_Componentes]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/02-Flujo_Sistema]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/03-Modelo_Datos]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/04-Modulos_Python]]
- GitHub: https://github.com/Bigsami89/Marcos2

---

*Proceso creado: 2026-03-19 | Ultima actualizacion: 2026-03-19*
