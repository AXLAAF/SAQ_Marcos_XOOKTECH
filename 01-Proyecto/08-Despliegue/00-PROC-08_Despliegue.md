# Proceso de Despliegue — XookTech

**Área de proceso:** Desarrollo de Software  
**Nombre del proceso:** Despliegue de sistemas a producción  
**Responsable:** Programador asignado o líder de proyecto  
**Entradas:** Código terminado con pruebas manuales realizadas  
**Salidas:** Sistema disponible para el cliente en su dominio, con acceso seguro y funcionando correctamente  
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

## Información Preliminar

Los documentos que se pueden necesitar en este proceso se listan a continuación.  
Los marcados como _[por crear]_ no existen todavía y se propone generarlos.

| Nombre del documento                    | Ubicación     |
| --------------------------------------- | ------------- |
| Registro de entornos y servidores       | [[01-Proyecto/08-Despliegue/Documentos_Apoyo/01-Registros/REG-08-01_Entornos_Servidores\|REG-08-01]] |
| Lista de Verificación de Despliegue     | [[01-Proyecto/08-Despliegue/Documentos_Apoyo/02-Formatos/CL-08-01_Verificacion_Despliegue\|CL-08-01]] |
| Documento de configuración del proyecto | [[01-Proyecto/08-Despliegue/Documentos_Apoyo/02-Formatos/FOR-08-01_Configuracion_Proyecto\|FOR-08-01]] |
| Registro de incidentes en producción    | [[01-Proyecto/08-Despliegue/Documentos_Apoyo/01-Registros/REG-08-02_Incidentes_Produccion\|REG-08-02]] |

---

## Proceso

### 1. Verificar que el código está listo para desplegarse

**Actualmente:**

- Se considera que el código está listo cuando el programador terminó de escribirlo y realizó pruebas manuales.
- No existe un criterio formal que defina qué significa "terminado" ni qué flujos deben haberse probado antes de desplegar.

**NT-1:** Desplegar con base en la percepción de que "ya está listo" traslada los errores al ambiente del cliente. IEEE 12207:2017 (proceso de verificación) establece que antes de pasar a la siguiente etapa del ciclo de vida se debe confirmar, con criterios definidos, que la etapa anterior cumplió sus objetivos. Se propone una verificación mínima documentada antes de iniciar cualquier despliegue.

**Propuesta:**

- Antes de iniciar el despliegue, el responsable completa la Lista de Verificación de Despliegue ([[01-Proyecto/08-Despliegue/Documentos_Apoyo/02-Formatos/CL-08-01_Verificacion_Despliegue|CL-08-01]]).
- La lista debe confirmar como mínimo:
    - Los flujos principales del sistema fueron probados manualmente y funcionan.
    - No hay errores visibles en la consola del servidor ni en el navegador durante las pruebas.
    - Las variables de entorno y configuraciones del proyecto están documentadas y listas para el entorno de producción.
    - El código está subido al repositorio y corresponde a lo que se va a desplegar.
- Si algún punto de la lista no se cumple, no se inicia el despliegue hasta resolverlo.

---

### 2. Obtener el dominio

**Actualmente:**

- Se compra el dominio directamente o se solicita acceso al dominio del cliente según el caso.
- No queda registro de en qué plataforma se compró, con qué cuenta, ni quién tiene acceso.

**NT-2:** Los dominios representan la identidad del sistema en internet. Perder acceso a un dominio — por cambio de cuenta, contraseña olvidada o que el cliente lo gestione desde una plataforma que no se conoce — puede dejar el sistema fuera de línea por horas o días. Se propone registrar esta información desde el momento de la compra.

**Propuesta:**

- Al obtener el dominio, se registra en el Registro de entornos y servidores ([[01-Proyecto/08-Despliegue/Documentos_Apoyo/01-Registros/REG-08-01_Entornos_Servidores|REG-08-01]]):
    - Nombre del dominio.
    - Plataforma donde está registrado (ejemplo: Namecheap, GoDaddy, etc.).
    - Correo o cuenta con la que se gestionó.
    - Fecha de vencimiento del dominio.
    - Quién tiene acceso y cómo.
- Si el dominio pertenece al cliente, se solicita acceso al panel de DNS por escrito y se confirma antes de continuar.

---

### 3. Contratar y configurar el servidor

**Actualmente:**

- Se renta un servidor web compartido o un VPS con CloudPanel según el proyecto.
- No existe un criterio documentado para decidir cuándo usar uno u otro.
- No queda registro de las credenciales ni de cómo está configurado el servidor.

**NT-3:** Cada proyecto puede requerir un tipo de servidor diferente según su volumen de usuarios, el lenguaje en que está escrito, y si necesita procesos en segundo plano. Tomar esa decisión sin criterios escritos significa que depende de quien haga el despliegue ese día. SWEBOK v3 (Gestión de la Configuración del Software) señala que los entornos donde opera el software son parte de la configuración del sistema y deben estar documentados.

**Propuesta:**

- Se elige el tipo de servidor con base en las características del proyecto:
    - [PENDIENTE: definir los criterios del equipo para elegir entre servidor compartido y VPS.]
- Al contratar el servidor, se registra en el Registro de entornos y servidores ([[01-Proyecto/08-Despliegue/Documentos_Apoyo/01-Registros/REG-08-01_Entornos_Servidores|REG-08-01]]):
    - Proveedor del servidor.
    - Tipo de servidor contratado.
    - Sistema operativo y versión.
    - Dirección IP.
    - Cuenta con la que se contrató.
    - Accesos: usuario, método de autenticación.
- Si se usa CloudPanel u otro panel de administración, se registra también el acceso a ese panel.

---

### 4. Enlazar el dominio con el servidor

1. Se accede al panel de administración del dominio con las credenciales registradas en el paso anterior.
2. Se configuran los registros DNS para apuntar al servidor:
    - Se agrega o modifica el registro A con la dirección IP del servidor.
    - Si aplica, se agregan registros adicionales (correo, subdominios, etc.).
3. Se espera a que los cambios de DNS se propaguen. Este proceso puede tomar entre unos minutos y 48 horas dependiendo del proveedor.
4. Se verifica que el dominio responde correctamente antes de continuar.

**NT-4:** Los cambios de DNS tienen un tiempo de propagación que no se puede eliminar. Planear el despliegue sin considerar este tiempo puede retrasar la entrega. Se recomienda realizar el enlace del dominio el día anterior al despliegue cuando sea posible, para que la propagación no afecte los tiempos acordados con el cliente.

---

### 5. Subir los archivos del proyecto al servidor

**Actualmente:**

- Los archivos se suben manualmente al servidor a través de SSH o FTP.
- No hay un repositorio enlazado al servidor que automatice este paso.
- No existe un criterio definido sobre qué archivos se suben y cuáles no.

**NT-5:** Subir archivos manualmente introduce el riesgo de omitir archivos, subir versiones incorrectas, o sobreescribir cambios sin darse cuenta. IEEE 12207:2017 (proceso de integración del software) establece que el paso de integración debe ser repetible y verificable. Un proceso manual no lo es. Se propone avanzar hacia un proceso más confiable aunque sea de forma gradual.

**Propuesta a corto plazo** (sin cambiar la forma de trabajo actual):

- Antes de subir los archivos, se confirma en el repositorio que la versión que se va a subir corresponde exactamente al código que se probó.
- Se define una lista de archivos y carpetas que no se deben subir al servidor ([ver Lista de Verificación de Despliegue — por crear]). Ejemplos: carpetas de dependencias instalables localmente, archivos de configuración local, archivos de prueba.
- Se sube el proyecto mediante SSH o FTP.
- Al terminar, se verifica que la estructura de archivos en el servidor coincide con lo esperado.

**NT-6:** El paso siguiente en madurez del proceso sería enlazar el repositorio directamente al servidor para que los despliegues se hagan desde el repositorio y no de forma manual. Esto elimina los errores de omisión y hace que cada despliegue sea rastreable. SWEBOK v3 (Gestión de la Configuración del Software) lo describe como parte de la gestión del entorno de construcción. Este cambio no tiene que hacerse de inmediato, pero sí debe ser la dirección del equipo.

---

### 6. Configurar las variables del entorno de producción

**Actualmente:**

- Se modifican los archivos `.env` o la carpeta `/Core` del proyecto directamente en el servidor.
- No existe un documento que describa qué variables deben configurarse ni qué valor debe tener cada una en producción.

**NT-7:** Las variables de entorno contienen información sensible (contraseñas, llaves de acceso, cadenas de conexión a base de datos). Configurarlas de memoria o buscándolas en el código cada vez que se hace un despliegue aumenta el riesgo de errores y de exponer información. Se propone documentar qué variables existen, qué significan y cómo deben configurarse en cada entorno, sin registrar los valores sensibles en documentos compartidos.

**Propuesta:**

- Existe un Documento de configuración del proyecto ([[01-Proyecto/08-Despliegue/Documentos_Apoyo/02-Formatos/FOR-08-01_Configuracion_Proyecto|FOR-08-01]]) que describe:
    - Qué variables de entorno requiere el proyecto.
    - Qué significa cada variable.
    - Qué valor de ejemplo o formato se espera (no el valor real).
    - Si la variable cambia entre el entorno de desarrollo y el de producción.
- El responsable del despliegue consulta este documento para configurar las variables en el servidor.
- Los valores reales de producción (contraseñas, llaves) se guardan en [PENDIENTE: definir dónde se almacenan las credenciales de producción — puede ser un gestor de contraseñas del equipo u otro medio que el equipo acuerde].
- Una vez configuradas las variables, se verifica que el sistema arranca sin errores de configuración antes de continuar.

---

### 7. Configurar el acceso seguro mediante HTTPS

1. Se genera el certificado de seguridad para el dominio. El método depende del servidor:
    - Si se usa CloudPanel u otro panel de administración: se activa el certificado desde el panel.
    - Si se gestiona directamente el servidor: se usa Let's Encrypt mediante la herramienta `certbot`.
2. Se verifica que el dominio responde correctamente con el protocolo seguro.
3. Se configura que cualquier acceso sin protocolo seguro sea redirigido automáticamente al acceso seguro.
4. Se registra la fecha de vencimiento del certificado en el Registro de entornos y servidores.

**NT-8:** Los certificados de Let's Encrypt tienen una duración de 90 días. Si no se renueven, el sistema muestra una advertencia de seguridad que impide el acceso normal de los usuarios. Si el servidor no renueva el certificado de forma automática, se debe registrar una fecha de revisión antes del vencimiento. SWEBOK v3 (Calidad del Software) señala que la disponibilidad y seguridad del sistema son atributos de calidad que deben mantenerse, no solo configurarse una vez.

---

### 8. Configurar los procesos en segundo plano (cuando aplique)

Este paso aplica cuando el sistema tiene procesos que deben ejecutarse de forma continua en el servidor — por ejemplo, un servidor de aplicaciones, un manejador de colas, o un proceso de Node.js / Python / otro lenguaje.

1. Se crea el archivo de configuración del servicio en el sistema operativo del servidor.
2. Se define que el servicio se inicia automáticamente cuando el servidor se reinicia.
3. Se inicia el servicio y se verifica que está funcionando.
4. Se registra en el Registro de entornos y servidores el nombre del servicio y el comando para revisarlo, iniciarlo y detenerlo.

**NT-9:** Si el servidor se reinicia por mantenimiento o falla y el proceso no está configurado para iniciarse automáticamente, el sistema queda fuera de línea hasta que alguien lo noten y lo inicien a mano. Registrar el nombre y los comandos del servicio garantiza que cualquier integrante del equipo puede resolver esto sin buscar cómo se llamó el proceso en ese proyecto específico.

---

### 9. Realizar pruebas en producción antes de notificar al cliente

**Actualmente:**

- Se hacen pruebas manuales de los flujos de trabajo que se identificaron como el camino esperado (happy path).
- No existe un listado formal de qué flujos deben probarse ni cómo se registra el resultado.

**NT-10:** Las pruebas manuales sin un listado de referencia dependen de la memoria de quien las hace ese día. IEEE 1028-2008 (Estándar para Revisiones e Inspecciones de Software) señala que cualquier actividad de verificación debe estar guiada por criterios definidos para ser repetible y confiable. Probar en producción sin un listado puede dejar fuera flujos importantes y detectarlos solo cuando el cliente los reporta.

**Propuesta:**

- Se utiliza la Lista de Verificación de Despliegue ([[01-Proyecto/08-Despliegue/Documentos_Apoyo/02-Formatos/CL-08-01_Verificacion_Despliegue|CL-08-01]]) para guiar las pruebas en producción.
- La lista incluye los flujos de trabajo principales del sistema, definidos antes del despliegue.
- Para cada flujo se registra: si pasó, si falló, y si falló, qué se observó.
- Si algún flujo falla, se corrige antes de notificar al cliente.
- Si la corrección requiere un cambio significativo, se repiten las pruebas desde este paso.

---

### 10. Notificar al cliente

**Actualmente:**

- Se informa al cliente de manera verbal o por mensaje que el sistema ya está disponible.
- No queda registro de cuándo se entregó ni qué versión se entregó.

**NT-11:** La notificación de entrega es también el punto de inicio de la responsabilidad del cliente sobre el sistema. Si no queda registro de cuándo se entregó y en qué estado estaba, cualquier problema posterior es difícil de ubicar en el tiempo. IEEE 12207:2017 (proceso de entrega) establece que la transferencia del producto al cliente debe quedar documentada.

**Propuesta:**

- Se notifica al cliente por escrito (correo o mensaje en la plataforma de comunicación que usen) indicando:
    - Que el sistema está disponible en su dominio.
    - La dirección web donde puede acceder.
    - Los accesos iniciales si aplica (usuario y contraseña provisional).
    - Cualquier indicación necesaria para comenzar a usarlo.
- Se guarda una copia de esta notificación en el expediente del proyecto.

---

## Justificación de Mejoras

**NT-1 — Verificación formal antes de desplegar**  
El criterio de "ya está listo" es subjetivo y varía entre personas. IEEE 12207:2017 (proceso de verificación) establece que la transición entre etapas del ciclo de vida debe estar respaldada por criterios definidos. Una lista de verificación no elimina los errores, pero sí reduce los más frecuentes y hace el proceso repetible.

**NT-2 — Registro del dominio**  
La pérdida de acceso a un dominio es uno de los incidentes más costosos en operación porque puede dejar el sistema fuera de línea sin que el equipo de desarrollo pueda actuar rápidamente. SWEBOK v3 (Gestión de la Configuración del Software) incluye la gestión del entorno de operación como parte de la configuración del sistema.

**NT-3 — Documentar la configuración del servidor**  
El conocimiento sobre cómo está configurado un servidor no debe vivir solo en la memoria de quien lo configuró. Si esa persona no está disponible cuando ocurre un problema, el tiempo de recuperación aumenta de forma innecesaria. SWEBOK v3 considera el entorno de operación parte de la configuración del sistema y, por tanto, sujeto a registro y control.

**NT-4 — Considerar la propagación de DNS en la planeación**  
La propagación de DNS no es un problema técnico evitable — es una característica de cómo funciona el sistema de nombres de internet. Reconocerla como parte del proceso y planear alrededor de ella es una práctica básica de gestión de despliegues.

**NT-5 y NT-6 — Subida de archivos confiable y rastreable**  
IEEE 12207:2017 (proceso de integración) requiere que el paso de integración sea verificable y repetible. Un proceso manual donde los archivos se seleccionan de memoria no cumple ninguno de los dos requisitos. El paso a un despliegue desde repositorio no tiene que ser inmediato, pero sí debe ser la dirección del equipo.

**NT-7 — Documentar las variables de entorno**  
Las variables de entorno son parte de la configuración del sistema tanto como el código. No documentarlas genera dependencia del conocimiento de una sola persona. SWEBOK v3 (Gestión de la Configuración del Software) incluye la configuración del entorno como parte del sistema que debe gestionarse.

**NT-8 — Seguimiento al vencimiento del certificado HTTPS**  
Un certificado vencido interrumpe el acceso de todos los usuarios al sistema. Let's Encrypt ofrece renovación automática, pero esta debe configurarse correctamente. SWEBOK v3 (Calidad del Software) trata la disponibilidad del sistema como un atributo de calidad que debe mantenerse de forma continua, no solo en el momento de la configuración inicial.

**NT-9 — Registro de procesos en segundo plano**  
Los procesos en segundo plano son parte del sistema y deben ser tan rastreables como el código. Si un proceso falla o el servidor se reinicia, cualquier integrante del equipo debe poder restablecer el servicio sin depender de quien lo configuró originalmente.

**NT-10 — Lista de verificación para pruebas en producción**  
IEEE 1028-2008 establece que las actividades de verificación deben estar guiadas por criterios definidos. Las pruebas de memoria no son repetibles: lo que se prueba depende de quién hace el despliegue ese día y de cuánto recuerda. Una lista fija garantiza que los flujos más importantes siempre se revisen.

**NT-11 — Notificación escrita al cliente**  
La notificación escrita de entrega cumple dos funciones: informa al cliente de forma clara y genera un registro que ubica en el tiempo el estado del sistema en el momento de la entrega. IEEE 12207:2017 (proceso de entrega) establece que la transferencia del producto debe quedar documentada.

---

## Referencias

[1] SWEBOK v3.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2014. Capítulos consultados: Gestión de la Configuración del Software, Calidad del Software.

[2] IEEE 12207:2017. _Ingeniería de Sistemas y Software — Procesos del Ciclo de Vida del Software_. IEEE/ISO. Procesos consultados: Verificación, Integración, Entrega.

[3] IEEE 1028-2008. _Estándar para Revisiones e Inspecciones de Software_. IEEE.

[4] Registro de entornos y servidores. _[por crear]_ — Documento interno para registrar los datos de dominio, servidor, accesos y fechas de vencimiento de cada proyecto.

[5] Lista de Verificación de Despliegue. _[por crear]_ — Lista que el responsable completa antes y después del despliegue para verificar que el sistema cumple los criterios mínimos antes de notificar al cliente.

[6] Documento de configuración del proyecto. _[por crear]_ — Documento que describe las variables de entorno que requiere cada proyecto, su significado y el formato esperado para cada entorno.