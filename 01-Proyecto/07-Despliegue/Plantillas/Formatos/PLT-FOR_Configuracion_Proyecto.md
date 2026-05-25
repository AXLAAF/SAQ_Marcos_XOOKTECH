# [PLT-FOR_Configuracion_Proyecto] Configuración del Proyecto

## Metadatos del Documento
| Campo | Valor |
|---|---|
| Proyecto | |
| Proceso | Despliegue (PROC-07) |
| Responsable | Líder de Desarrollo e Implementación |
| Estándar de referencia | ISO/IEC 12207 / SWEBOK v4 |

---

## 1. Requisitos del Entorno (Línea Base de Software)
*   **Lenguaje y Runtime:** (Ej: Python v3.12.0)
*   **Base de Datos Relacional:** (Ej: SQLite v3 / PostgreSQL v16)
*   **Librerías Críticas y Versión:**
    *   OpenCV: (Ej: opencv-python v4.9.0)
    *   Flask: (Ej: Flask v3.0.2)
    *   Pillow: (Ej: Pillow v10.2.0)

---

## 2. Variables de Entorno (.env.example)
Variables necesarias para inicializar la aplicación. **PROHIBIDO colocar valores confidenciales reales aquí**.

| Variable | Descripción técnica | ¿Es crítica en producción? |
|:---|:---|:---|
| `FLASK_ENV` | Define el entorno de ejecución (development/production) | Sí |
| `SECRET_KEY` | Llave criptográfica para firma de cookies | Sí |
| `DB_PATH` | Ruta absoluta al catálogo de base de datos | Sí |
| `API_KEY` | Token de acceso a servicios externos | Sí |

---

## 3. Comandos Estándar de Instalación y Despliegue
1.  **Inicialización del Entorno Aislado:**
    ```bash
    python -m venv env
    source env/bin/activate
    ```
2.  **Sincronización de Dependencias:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Ejecución con Servidor WSGI (Gunicorn):**
    ```bash
    gunicorn --workers 3 --bind 127.0.0.1:5000 app:app
    ```

---

## 4. Historial de Versiones de Plantilla
| Versión | Fecha | Autor | Modificación |
|---|---|---|---|
| 1.0 | 2026-05-24 | Líder de Desarrollo | Creación e implantación inicial. |
