# Plantilla de Diagrama de Arquitectura

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Especificación de Requisitos y decisiones técnicas.  
**Salidas:** Diagramas de arquitectura del sistema en Mermaid.js.  

---

## 1. Guía de Estilo

Los diagramas técnicos deben escribirse utilizando **Mermaid.js** para que se rendericen directamente en Obsidian. Se prohíbe el uso de imágenes externas.

---

## 2. Diagramas de Ejemplo

### 2.1 Vista Lógica (Descomposición de Componentes)

```mermaid
graph TD
    subgraph Frontend["Capa Cliente (Vista)"]
        UI["Interfaz de Usuario"]
        JS["Lógica de Cliente (JavaScript)"]
    end

    subgraph Backend["Capa Servidor (Lógica)"]
        Rutas["Rutas y Controladores"]
        Servicios["Lógica de Negocio"]
    end

    subgraph Persistencia["Capa de Persistencia"]
        DB["Base de Datos"]
    end

    UI --> Rutas
    JS --> Rutas
    Rutas --> Servicios
    Servicios --> DB
```

### 2.2 Vista de Comportamiento (Secuencia)

```mermaid
sequenceDiagram
    actor Usuario
    participant UI as Interfaz Cliente
    participant Backend as Servidor Backend
    participant DB as Base de Datos

    Usuario->>UI: [Acción del usuario]
    UI->>Backend: [Petición HTTP]
    Backend->>DB: [Consulta / Guardado]
    DB-->>Backend: [Resultado de datos]
    Backend-->>UI: [Respuesta de datos]
    UI-->>Usuario: [Visualización]
```

### 2.3 Estructura Física (Estructura de Directorios)

```
proyecto/
├── app/
│   ├── __init__.py
│   ├── rutas.py
│   ├── modelos.py
│   └── servicios.py
├── static/
│   ├── css/
│   └── js/
├── templates/
├── tests/
├── requirements.txt
└── config.py
```

---

## 3. Control del Artefacto
* **Código de documento:** DIA-VAL-XX  
* **Estándar:** IEEE 1016  
* **Estado:** [Pendiente / Aprobado]  
