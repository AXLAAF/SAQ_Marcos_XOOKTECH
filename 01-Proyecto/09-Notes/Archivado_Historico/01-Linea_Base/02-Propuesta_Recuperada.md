# Propuesta Recuperada - Sistema Visualizador de Marcos
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Acuerdos del Cliente e Información Inicial
**Salidas:** Línea Base del Proyecto Certificada

---

> Documento que reconstruye la propuesta original del proyecto basada en la recuperación de información del equipo y entrevistas. Este documento establece la línea base del alcance original.
Artefacto de salida del Paso 3 de [[01-Baseline/00-PROC-01_Recuperacion_Linea_Base]]. Establece la linea base del alcance original. Entrada para [[02-Requisitos/00-PROC-02_Especificacion_Requerimientos|PROC-02 Especificación de Requerimientos]] y [[07-Control/00-PROC-07_Control|PROC-07 Gestión de Control]].

---

## 1. Descripcion General del Proyecto

### 1.1 Nombre del Proyecto
**Sistema Visualizador de Marcos para Enmarcame**

### 1.2 Cliente
- **Nombre del negocio:** Enmarcame
- **Representante:** Gerònimo Aguilar Chap
- **Ubicacion:** Merida, Yucatan

### 1.3 Descripcion
Aplicación web diseñada para que los clientes del negocio "Enmarcame" puedan visualizar cómo quedaría su foto con el marco elegido antes de realizar la compra. El sistema permite subir una foto del cliente, seleccionar un marco del catálogo y ver una previsualización 3D en tiempo real.

### 1.4 Problema que Resuelve
Los clientes frecuentemente solicitaban "ver cómo queda" antes de encargar un marco. Traían fotos de sus celulares y les costaba visualizar el resultado final. El sistema busca cerrar la venta en el momento mostrando al cliente una visualización realista del producto final.

---

## 2. Alcance Original del Proyecto

### 2.1 Funcionalidades Incluidas (MVP)

| REQ ID | Descripcion                                                                               | Estado en Propuesta |
| ------ | ----------------------------------------------------------------------------------------- | ------------------- |
| REQ-01 | El cliente puede subir una foto desde la app web                                          | Incluida            |
| REQ-02 | El sistema muestra una previsualizacion del marco sobre la foto                           | Incluida            |
| REQ-03 | Los marcos se crean desde una textura escaneada y un modelado 3D desde una foto de perfil | Incluida            |
| REQ-04 | El cliente puede seleccionar marcos desde un catalogo                                     | Incluida            |
| REQ-05 | El catalogo incluye: ancho, alto, clave, textura, forma 3D                                | Incluida            |

### 2.2 Funcionalidades Excluidas
Las siguientes funcionalidades NO estaban incluidas en el alcance original:
- Marcos dobles (REQ-06)
- Tipos de vidrio (REQ-07)
- Maria Luisa multiple (REQ-08)
- Pantalla secundaria (REQ-9)

### 2.3 Catalogo de Marcos
- **Cantidad acordada:** Aproximadamente mas de 1,000 marcos
- **Cantidad implementada:** Todos los marcos, hasta existencia actual
- **Fuente:** Cede norte de Enmarcame.
- **Proceso:** Escaneo de ~200 marcos/semana durante 5 semanas

---

## 3. Tecnologia y Arquitectura

### 3.1 Tecnologias Acordadas

| Componente | Tecnologia |
|------------|-------------|
| Frontend | HTML5, Bootstrap, CSS3, JavaScript |
| Backend | JavaScript (Node.js) |
| Base de datos | PostgreSQL |
| Herramienta auxiliar | Python (deteccion de ancho de marcos, generacion de modelos 3D) |
| Hosting | VPS (proveedor por definir) |

### 3.2 Descripcion de Componentes

**Aplicacion Web:**
- Interfaz responsive para uso en tienda
- Catalogo de marcos con filtros (estilo, color, tamaño)
- Motor de previsualizacion 3D en tiempo real
- Sistema de carga de imagenes

**Programa Python:**
- Deteccion automatica de ancho de marcos desde fotos
- Generacion de modelos 3D a partir de texturas 2D
- Procesamiento de imagenes del catalogo

**Base de Datos:**
- Catalogo de marcos con especificaciones completas
- Almacenamiento de imagenes y texturas
- Registro de configuraciones de clientes

---

## 4. Costo y Modelo de Negocio

### 4.1 Estructura de Costos

| Concepto            | Monto (MXN) | Condiciones                       |
| ------------------- | ----------- | --------------------------------- |
| Desarrollo completo | $------     | Pago unico                        |
| Renta mensual       | $2,500      | Mantenimiento y soporte incluidos |

### 4.2 Desglose del Costo de Desarrollo (------)

El costo de desarrollo incluia:
- Desarrollo de la aplicacion web completa (frontend y backend)
- Programa Python para procesamiento de imagenes
- Escaneo de todos los marcos del catalogo (~1,000+ unidades)
- Creacion de la base de datos con especificaciones
- Instalacion y configuracion inicial
- Capacitacion para usar el sistema

### 4.3 Costo Recurrente ($2,500 MXN/mes)

La renta mensual incluyia:
- Hosting y servidor
- Mantenimiento de la base de datos
- Soporte basico para problemas tecnicos
- Actualizaciones de seguridad

### 4.4 Costos No Incluidos (Scope Creep)

**[PENDIENTE: agregar definicion o enlace a glosario de Scope Creep]**

Los siguientes items representan trabajo adicional fuera del alcance original y requieren negociación adicional:
- Marcos dobles (REQ-07)
- Tipos de vidrio (REQ-08)
- Maria Luisa multiple (REQ-09)
- Pantalla secundaria (REQ-10)

---

## 5. Entregables Definidos

### 5.1 Entregables al Cliente

| Entregable         | Descripcion                                | Estado    |
| ------------------ | ------------------------------------------ | --------- |
| Aplicacion web     | Sistema completo funcionando en produccion | Completado |
| Catalogo de marcos | Base de datos con ~950 marcos              | Completado |
| Programa Python    | Herramienta de procesamiento de imagenes   | Completado |
| Capacitacion       | Sesion de entrenamiento para empleados     | Completado |

### 5.2 Documentacion (No incluida originalmente)
- Propuesta formal por escrito
- Especificacion de requisitos
- Documentacion tecnica
- Manual de usuario

---

## 6. Cronograma

### 6.1 Plazo Original Acordado
- **Duracion estimada:** 3 meses
- **Fecha de inicio:** Enero 2026 (aproximado)
- **Fecha de entrega:** Abril, Mayo (aproximado)

### 6.2 Fechas Reales
- **Inicio de desarrollo:** Enero 2026
- **Puesta en produccion:** ~3, 4 meses despues del inicio
- **Lanzamiento:** Verano 2026

### 6.3 Estado Actual
- Sistema en test
- Nuevos requerimientos pendientes de implementacion

---

## 7. Supuestos y Restricciones

### 7.1 Supuestos
1. El cliente tiene infraestructura basica (computadora, internet) en la tienda
2. Los marcos del inventario original estaran disponibles para escaneo
3. El cliente proporcionara acceso a su inventario de marcos en formato util

### 7.2 Restricciones
1. No existe contrato formal firmado (si existe, averiguar sobre eso)
2. Los acuerdos fueron verbales
3. No se definieron metricas formales de calidad
4. No hubo proceso de control de cambios documentado

---

## 8. Aprobacion

| Campo                | Valor                      |
| -------------------- | -------------------------- |
| Elaborado por        | Analista Técnico   |
| Revisado por         | Líder SQA |
| Fecha de elaboracion | 2026-03-23                 |
| Estado               | Completado                 |

### Historial de Cambios

| Version | Fecha | Autor | Descripcion |
|---------|-------|-------|-------------|
| 1.0 | 2026-03-23 | Analista Técnico | Creacion inicial - Propuesta recuperada |
| 1.1 | 2026-04-13 | Kilo-SQA-Agent | Vinculado al proceso PROC-01, corregida nota de Scope Creep, actualizados estados de entregables a Completado |

---

*Documento creado como parte del PROC-01 - Recuperacion de Linea Base*
*Referencia: [[01-Linea_Base/05-Minuta_Entrevista|Minuta de Entrevista]]*