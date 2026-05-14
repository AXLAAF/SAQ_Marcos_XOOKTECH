---
id: CTX-01
titulo: Contexto del Proyecto - Sistema Visualizador de Marcos
version: "2.0"
estado: Activo
tipo: Contexto
responsable: Axel Morales
cliente: Enmarcame
equipo:
  - Axel Morales (SQA Lead)
  - Samuel Blanco (Dev/Ops)
  - Carlos Yonson (Analyst)
tags:
  - contexto
  - linea-base
  - enmarcame
---

# Contexto del Proyecto: Visualizador de Marcos "Enmarcame"

## 1. Identificacion del Problema (Realidad del Negocio)
El cliente **"Enmarcame"** enfrenta una perdida economica significativa debido al desperdicio de materia prima, especificamente **madera Banak** y molduras de aluminio. El problema reside en el error humano durante la toma de medidas manuales y la dificultad del cliente final para visualizar como quedara su obra con un **marco doble** o con una **Maria Luisa** de dimensiones especificas.

Actualmente, si una moldura se corta mal por una mala interpretacion del diseño, la pieza de madera queda inutilizada, aumentando los costos de operacion en un 15%.

## 2. La Solucion Tecnica (El Prototipo)
Se propone el desarrollo de un **Sistema Visualizador de Marcos** que automatice la toma de decisiones y reduzca el margen de error.

### Componentes Clave:
- **Vision Artificial (OpenCV)**: Implementacion de algoritmos de deteccion de aristas (Canny) para identificar el ancho real de la moldura desde una foto patron.
- **Renderizado Dinamico (Pillow)**: Modulo de procesamiento de imagenes para superponer capas de marcos y vidrios en tiempo real sobre la fotografia cargada.
- **Interfaz Web (Flask)**: Plataforma de interaccion para el usuario y visualizacion en pantalla secundaria (REQ-10) para el cliente en tienda.

## 3. Estrategia de Aseguramiento de la Calidad (SQA)
El proyecto no solo es un desarrollo de software, sino un ejercicio de rigor bajo el modelo **ETVX** y los estandares de **Daniel Galin** y **SWEBOK v4**.

### Ciclo de Vida de 8 Fases:
1.  **Linea Base**: Definicion de este contexto y acuerdos iniciales.
2.  **Requisitos**: Especificacion profunda de REQ-01 a REQ-10 (Carlos Yonson).
3.  **Diseño**: Arquitectura DIS y modelo de datos (Axel Morales).
4.  **Codificacion**: Implementacion de modulos Python (Samuel Blanco).
5.  **Pruebas**: Verificacion y Validacion con evidencia real (Axel Morales).
6.  **Mantenimiento**: Estrategia de soporte post-entrega (Samuel Blanco).
7.  **Control**: SCM, Inspecciones y Metricas (Carlos Yonson).
8.  **Despliegue**: Puesta en produccion en "Enmarcame" (Samuel Blanco).

## 4. Herramientas de Trabajo
- **Obsidian**: Fuente unica de verdad para el SGC (Vault sistematizado).
- **GitHub**: Repositorio `Bigsami89/Marcos2` para el control de versiones del codigo.
- **Libros Base**: Lewis (Testing), Galin (SQA), O'Regan (Quality).

---
*Ultima actualizacion: 2026-05-12 | Por Axel Morales (SQA Lead)*
