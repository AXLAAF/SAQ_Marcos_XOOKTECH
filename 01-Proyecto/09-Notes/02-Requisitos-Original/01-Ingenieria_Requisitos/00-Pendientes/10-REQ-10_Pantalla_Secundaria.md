
# REQ-10: Pantalla Secundaria para Previsualizacion
**Responsable:** Analista de Requerimientos
**Entradas:** Línea Base y Especificaciones Iniciales
**Salidas:** Matriz de Trazabilidad e Requisitos Formales

---

## 1. Descripcion General

El sistema debe poder proyectar la previsualizacion en una pantalla secundaria (por ejemplo, un TV o monitor adicional) para que el cliente pueda ver el resultado en una pantalla mas grande mientras el empleado opera el sistema. Esta funcionalidad fue solicitada por el cliente despues de la implementacion inicial del sistema (Scope Creep).

> **Nota**: Este requerimiento representa un cambio al alcance original del proyecto. Esta documentado en [[05-Control de cambios/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]] para control de cambios.

## 2. Reglas de Negocio

- RN-10-01: La pantalla secundaria es opcional, el sistema funciona sin ella
- RN-10-01: La sincronizacion entre pantalla principal y secundaria debe ser en tiempo real
- RN-10-02: El contenido proyectado es solo la previsualizacion (no la interfaz de control)
- RN-10-03: El sistema detecta automaticamente cuando se conecta una segunda pantalla

## 3. Precondiciones

- El sistema tiene la funcionalidad de previsualizacion basica (REQ-02)
- Existe una segunda pantalla disponible y conectada
- El navegador soporta la API de pantalla extendida

## 4. Flujo Principal (Happy Path)

1. El empleado opera el sistema en la pantalla principal (computadora)
2. El cliente esta frente a la pantalla secundaria (TV)
3. Cuando el empleado selecciona un marco, la previsualizacion aparece en ambas pantallas
4. El empleado puede continuar operando mientras el cliente ve el resultado en grande
5. La sincronizacion es en tiempo real (menos de 500ms)

## 5. Flujos Alternativos

| FA-ID | Condicion Disparadora | Respuesta del Sistema |
|-------|------------------------|----------------------|
| FA-01 | No hay pantalla secundaria conectada | El sistema funciona normalmente en la pantalla principal |
| FA-02 | La pantalla secundaria se desconecta durante el uso | El sistema continua funcionando y avisa al empleado |

## 6. Flujos de Excepcion

| FE-ID | Condicion de Error | Respuesta del Sistema |
|-------|--------------------|----------------------|
| FE-01 | El navegador no soporta pantalla extendida | Se muestra un mensaje y se usa solo la pantalla principal |
| FE-02 | La sincronizacion falla | El sistema reintenta la conexion automaticamente |

## 7. Criterios de Aceptacion (formato BDD)

| CA-ID | Dado | Cuando | Entonces |
|-------|------|--------|----------|
| CA-01 | Se conecta una segunda pantalla | Se detecta la pantalla | El sistema pregunta si desea proyectar la previsualizacion |
| CA-02 | El empleado selecciona un marco en la pantalla principal | Se actualiza la previsualizacion | La pantalla secundaria muestra el mismo contenido en menos de 500ms |
| CA-03 | No hay pantalla secundaria disponible | El sistema inicia | Funciona normalmente sin errores |

## 8. Restricciones Tecnicas

- Tecnologia: WebRTC o Screen Capture API
- Soporte: Navegadores modernos (Chrome, Firefox, Edge)
- Resolucion maxima en pantalla secundaria: 4K

## 9. Dependencias

- [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02 Previsualización Marco]] - Requerimiento base de previsualizacion
- [[05-Control de cambios/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]] - Change Request asociado

## 10. Trazabilidad

- Casos de Prueba: [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Pantalla_Secundaria/01-CP-13_Proyeccion]], [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Pantalla_Secundaria/02-CP-14_Sync_tiempo_real]], [[06-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Pantalla_Secundaria/03-CP-15_Fallback_sin_pantalla]]
- Change Requests: [[05-Control de cambios/01-Ingenieria_Control/11-CR-04_Pantalla_Secundaria|CR-04 Pantalla Secundaria]] (Pendiente de aprobacion.