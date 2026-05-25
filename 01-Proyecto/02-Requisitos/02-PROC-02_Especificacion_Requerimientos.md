# Proceso de Especificación de Requisitos — XookTech

**Código de Registro:** PROC-02-01  
**Responsable:** Analista de Requerimientos  
**Entradas:** Solicitud del Product Owner, Contrato de Desarrollo, Solicitudes de Cambio (CR-XXX).  
**Salidas:** Requisitos Aprobados (Fichas REQ BDD estables en 01-Aprobados), Matriz de Trazabilidad RTM (STD-03) sincronizada, Registro de Calidad SQA (REG-02-01).  
**Propósito:** Definir el procedimiento operativo estandarizado y sistemático para la captura, especificación en formato BDD, validación con el cliente e inyección en la Línea Base de todos los requerimientos del Visualizador de Marcos, bajo el rigor del Aseguramiento de Calidad (SQA) y el Ciclo Deming (PDCA).

---

## Información Preliminar

Los documentos e insumos necesarios para la ejecución del proceso se detallan a continuación:

| Nombre del documento                       | Ubicación en el Vault                                                                         |                           |
| ------------------------------------------ | --------------------------------------------------------------------------------------------- | ------------------------- |
| Minuta de Entrevista                       | [[09-Notes/01-Linea_Base-Original/05-Minuta_Entrevista                                        | 05-Minuta_Entrevista]]    |
| Acuerdos del Cliente                       | [[09-Notes/01-Linea_Base-Original/03-Acuerdos_Cliente                                         | 03-Acuerdos_Cliente]]     |
| Propuesta Recuperada                       | [[09-Notes/01-Linea_Base-Original/02-Propuesta_Recuperada                                     | 02-Propuesta_Recuperada]] |
| Matriz de Trazabilidad de Requisitos (RTM) | [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad                        | STD-03]]                  |
| Checklist de Verificación de Requisitos    | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos | CL-02]]                   |
| Ficha de REQ-01 Carga de Imagen            | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen                  | REQ-01]]                  |
| Ficha de REQ-02 Previsualización de Marco  | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco        | REQ-02]]                  |
| Ficha de REQ-03 Generación de Marcos 3D    | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/06-REQ-03_Generacion_Marcos_3D          | REQ-03]]                  |
| Ficha de REQ-04 Catálogo de Marcos         | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos               | REQ-04]]                  |
| Ficha de REQ-05 Filtrado de Catálogo       | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo             | REQ-05]]                  |
| Ficha de REQ-06 Datos del Catálogo         | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/04-REQ-06_Datos_Catalogo                | REQ-06]]                  |


---

## Proceso

Este proceso se rige bajo las fases del Ciclo Deming (PDCA) para asegurar la mejora continua y el control de calidad en cada etapa.

---

### Fase 1: Planeación (Planear)

Esta fase consiste en la preparación de los artefactos y la planificación de las reuniones de levantamiento con el Product Owner (PO).

1. **Paso 1: Agendar reunión:** El Analista de Requerimientos agenda una sesión formal con el PO para el levantamiento de requerimientos iniciales o el análisis de cambios, programando la llamada vía telefónica o por videollamada a través de Google Meet o Microsoft Teams. La sesión se agenda con un mínimo de 24 horas de anticipación.
2. **Paso 2: Confirmación:** Envía y recibe la confirmación escrita de la fecha y hora de la reunión. Si el PO no puede asistir, la reunión se reagenda repitiendo el paso 1.
3. **Paso 3: Preparación del Reporte:** Los analistas preparan una agenda preliminar y preguntas guía utilizando la plantilla de Reporte de Junta de XookTech, guardándola en la carpeta de trabajo del proyecto.
4. **Paso 4: Inicialización del Requisito:** El Analista de Requerimientos crea una nota física en estado Pendiente bajo `02-Requisitos/01-Ingenieria_Requisitos/00-Pendientes/REQ-XXX.md` por cada necesidad identificada en la planeación.
5. **Paso 5: Registro de Origen:** Asocia a la ficha el ID del requerimiento y la liga a la solicitud de cambio relacionada (Change Request) si proviene de un control de cambios.

---

### Fase 2: Especificación y Modelado (Hacer)

Esta fase comprende la redacción técnica estructurada y la ingeniería detallada de los requisitos capturados.

6. **Paso 6: Aplicar plantilla:** El Analista de Requerimientos edita la ficha `REQ-XXX.md` en la subcarpeta de pendientes y le inyecta la plantilla formal de especificación.
7. **Paso 7: Redacción de Reglas de Negocio:** Detalla y documenta de forma atómica todas las reglas de negocio técnicas (formatos admitidos JPEG/PNG, peso máximo de 10 MB, límites físicos del canvas y rendimiento).
8. **Paso 8: Modelar escenarios BDD:** Estructura los escenarios de aceptación bajo la notación Dado/Cuando/Entonces (Happy Path, flujos alternos y excepciones), asegurando que cada escenario sea medible y verificable por el equipo de pruebas.
9. **Paso 9: Mapeo de Trazabilidad Inicial:** Agrega en la ficha los links vacíos hacia los casos de diseño de la Fase 03 y los Casos de Prueba correspondientes de la Fase 05.
10. **Paso 10: Prototipado rápido:** El analista realiza un prototipo interactivo simplificado en el canvas de Obsidian para visualizar el comportamiento de las pantallas asociadas al requerimiento.

---

### Fase 3: Validación y Aprobación (Verificar)

Esta fase asegura que la especificación técnica desarrollada sea validada formalmente por el PO y aprobada de mutuo acuerdo.

11. **Paso 11: Sesión de Validación:** El Analista de Requerimientos presenta la especificación técnica BDD y el prototipo rápido al PO en sesión de revisión conjunta.
12. **Paso 12: Manejo de Cambios en Validación:** Si el PO solicita ajustes o no comprende la lógica, se registran las observaciones y se regresa a la Fase 2 (Paso 6) para re-especificar.
13. **Paso 13: Aprobación por Escrito:** Una vez que el PO esté conforme con todos los escenarios BDD, el Analista de Requerimientos solicita una aprobación formal y explícita por escrito (vía correo o mensaje oficial).
14. **Paso 14: Inyección de Evidencia:** El Analista de Requerimientos inyecta la captura o transcripción del correo de aprobación directamente en la sección "Evidencia de Aprobación" del archivo `REQ-XXX.md`.
15. **Paso 15: Actualizar Estado:** Cambia formalmente el estado de la nota en su metadata a Aprobado.

---

### Fase 4: Control de Configuración y Línea Base (Actuar)

Esta fase ejecuta la inyección oficial de los requerimientos aprobados a la Línea Base del SGC y el control de calidad independiente por SQA.

16. **Paso 16: Segregación Física:** El Analista de Requerimientos mueve físicamente la nota firmada `REQ-XXX.md` desde la carpeta de pendientes a la carpeta de aprobados oficiales `02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/`.
17. **Paso 17: Actualizar Matriz RTM:** Sincroniza la Matriz de Trazabilidad RTM (STD-03) mapeando bidireccionalmente el requerimiento aprobado con su caso de diseño de arquitectura y su caso de prueba en la Fase 05.
18. **Paso 18: Auditoría SQA Independiente:** El Analista de Control y Cambios ejecuta de forma independiente una auditoría sobre el requerimiento utilizando el checklist de requisitos CL-02.
19. **Paso 19: Registro de Aprobación de Calidad:**
    * **Caso A: Conforme:** Si la ficha cumple con el 100% de los criterios del checklist CL-02, el Analista de Control y Cambios firma el dictamen conforme en el registro REG-02-01, congelando el requerimiento en la Línea Base estable.
    * **Caso B: No Conforme:** Si se detectan ambigüedades o violaciones a los estándares, el Analista de Control y Cambios documenta el hallazgo y regresa la ficha a la subcarpeta de pendientes en estado Pendiente para su corrección (regresar al Paso 6).
20. **Paso 20: Derivación Operativa:** El requerimiento congelado se distribuye al Líder de Desarrollo como orden de trabajo (Fase 04) y al Analista de Pruebas para la automatización de sus casos de prueba (Fase 05).

---

## Justificación de Mejoras

* **Fase de Planeación:** Formalizar el agendamiento y contar con un Reporte de Junta previo evita desvíos de alcance desde el inicio de la fase.
* **Fase de Modelado BDD:** El formato Dado/Cuando/Entonces elimina ambigüedades lingüísticas y provee un insumo atómico y directamente medible para el equipo de verificación y desarrollo.
* **Fase de Validación:** Registrar explícitamente la confirmación escrita del Product Owner funciona como un control de seguridad contractual ante futuros desentendidos sobre el alcance del sistema.
* **Fase de Control de Configuración:** La segregación física entre pendientes y aprobados, complementada con el checklist CL-02 de SQA y el registro de calidad REG-02-01, garantiza que el equipo nunca codifique sobre especificaciones inestables o propensas a errores.

---

## Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Requisitos de Software.

[2] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Estructuración de Requisitos e Independencia).

[3] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Calidad Contractual e Infraestructura).

[4] CMMI-DEV v1.3. _CMMI para Desarrollo_, Software Engineering Institute. Áreas de proceso: Gestión de Requisitos (REQM) y Gestión de Configuración (CM).

[5] Auerbach Publications. _Software Testing and Continuous Quality Improvement, 2nd Edition_ (William E. Lewis, 2005).