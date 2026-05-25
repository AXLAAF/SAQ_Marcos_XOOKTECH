# CP-01: Validación de formato de imagen (Happy Path)
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Plan Maestro de Pruebas y Casos de Prueba
**Salidas:** Reporte de Ejecución y Defectos Registrados

---

## 1. Información del Caso de Prueba

| Campo | Valor |
|-------|-------|
| **ID** | CP-01 |
| **Módulo** | Carga de Imagen (Modulo-01) |
| **Tipo de Prueba** | Integración / API |
| **Requerimiento** | [[02-Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01: Carga de Imagen]] |
| **Prioridad** | Alta |
| **Estado** | Pendiente |

## 2. Descripción

Verificar que el servidor **Flask** acepta y procesa correctamente archivos de imagen en formato JPG, retornando un código de estado `200 OK` y el path temporal de la imagen.

## 3. Criterios de Aceptación

- **CA-01-01**: El sistema permite seleccionar un archivo .jpg desde el explorador.
- **CA-01-02**: El endpoint `/upload` procesa la petición sin errores de servidor.

## 4. Pasos de Ejecución

1. Iniciar el servidor Flask localmente.
2. Abrir la interfaz web en `http://localhost:5000`.
3. Hacer clic en "Subir Imagen" y seleccionar un archivo `test.jpg` (2MB).
4. Monitorear la consola del servidor y la pestaña "Network" del navegador.

## 5. Resultado Esperado

- **Navegador**: Muestra la previsualización de la imagen cargada.
- **Servidor (Log)**: `POST /upload 200 OK`.
- **API Response**: `{ "status": "success", "filename": "temp_test.jpg" }`.

## 6. Verificación de Éxito

- [ ] La imagen se visualiza en el Canvas.
- [ ] No hay errores de tipo MIME en el log de Flask.
- [ ] La interfaz permanece estable.

## 7. Trazabilidad

- **Plan Maestro**: [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]]
- **Diseño**: [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes|STD-04]]