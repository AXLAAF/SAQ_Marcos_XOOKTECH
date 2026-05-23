# Minuta de Entrevista - Recuperacion de Linea Base
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Acuerdos del Cliente e Información Inicial
**Salidas:** Línea Base del Proyecto Certificada

---

> Este documento contiene las respuestas a la Guía de Entrevista, representando las perspectivas de los miembros del equipo del proyecto.

---

## metadata de la Entrevista

| Campo                | Valor                       |
| -------------------- | --------------------------- |
| Fecha de realizacion | 2026-03-23                  |
| Duracion total       | 1 hora                      |
| Metodo               | Virtual                     |
| Participantes        | Líder SQA, Analista Técnico |
| Ubicacion            | Merida, Yucatan             |

---

## Bloque A: Contexto y Origen del Proyecto

### Pregunta A.1: ¿Cómo se originó el contacto con el cliente "Enmarcame"?

**Entrevistado (Líder SQA):** El contacto fue a través de un conocido común, no fue una propuesta fría ni publicidad. Un amigo en común nos presentó porque sabía que desarrollábamos aplicaciones web y conocía a Cliente, el dueño de Enmarcame. Él había expresado que quería "Algo para que los clientes vean sus cuadros antes de enmarcarlo" para su tienda, pero no tenía claro qué era exactamente. La primera reunión fue una llamada improvisada para escuchar unos requisitos preliminares y definir una primera reunion en su establecimiento

### Pregunta A.2: ¿Cuál fue la necesidad específica que el cliente expresó inicialmente?

**Entrevistado (Líder SQA):** Cliente nos dijo que sus clientes frecuentemente pedían "ver cómo queda" antes de encargar el marco. Muchas veces traían fotos de sus celulares y les costaba visualizar el resultado final, actualmente sin el sistema se utiliza la siguiente metodologia, utilizando esquinas de los materiales:
1. Se toma una moldura (De lo que se compone el marco)
2. Se toma una marialuisa
3. Se pone en la esquina de la obra (Si lo trae)
4. Se repite el proceso hasta que se llega a una combinacion al gusto del cliente

### Pregunta A.3: ¿Quiénes participaron en las primeras reuniones?

**Entrevistado (Líder SQA):** En la primera reunión estuvimos los dos, Cliente y yo. Fue una junta corta, como media hora, donde platicamos de todo: desde cómo funcionaba su negocio hasta qué esperaba del sistema. No había una propuesta formal, fue más una conversación para entender qué necesitaba.

### Pregunta A.4: ¿Cuál era el plazo original acordado?

**Entrevistado (Líder SQA):** Inicialmente acordamos se le dijo un plazo corto de 15 dias de desarrollo para para una entrega de lo platicado originalmente, aunque cuando nos dijo que no tenia una base de datos de sus marcos (Fotos, medidas y proveedor) se agrando el tiempo de 2 meses a 3 meses

### Pregunta A.5: ¿Existió alguna propuesta formal inicial?

**Entrevistado (Líder SQA):** No, y ese es uno de los problemas que queremos corregir ahora. No tenemos un documento formal de la propuesta. Todo quedó en conversaciones y acuerdos verbales. Lo que recuerdo es que le dijimos que el sistema le permitiría a sus clientes subir una foto, elegir un marco del catálogo y ver cómo quedaba. Costaría $24,000 pesos por todo el desarrollo y después $2,500 pesos mensuales de renta.

---

## Bloque B: Alcance del Proyecto - Requisitos Originales

### Pregunta B.1: ¿Cuál era la descripción del producto mínimo viable (MVP)?

**Entrevistado (Analista Técnico):** El minimo producto viable: Es aplicación web donde el cliente pudiera subir su foto, seleccionar un marco del catálogo y ver la previsualización. El catálogo inicial tendría los marcos que escaneáramos. No incluía nada de las peticiones de cambio al programa que vinieron después. puro básico.

### Pregunta B.2: ¿Qué funcionalidades debía incluir obligatoriamente?

**Entrevistado (Analista Técnico):** Lo que acordamos fue:
1. Subir imagen del cliente (REQ-01)
2. Ver previsualización del marco sobre la foto (REQ-02)
3. Catálogo de marcos con fotos y especificaciones (REQ-04 y REQ-06)
4. Motor que generara los marcos en 3D desde las texturas escaneadas (REQ-03)

No había más. Eso era todo. El catálogo se construiría con las fotos que escaneáramos, unas 1,000 molduras aproximadamente segun las anotaciones de Cliente.

### Pregunta B.3: ¿El cliente solicitó alguna funcionalidad que NO se implementó en la versión inicial?

**Entrevistado (Líder SQA):** En ese momento no, todo lo que pedimos lo implementamos. Lo que pasó es que después, ya en producción, empezó a surgir ideas nuevas. Esas fueron las que se convirtieron en los REQ-07 a REQ-10.

### Pregunta B.4: ¿Cuáles fueron los criterios de aceptación?

**Entrevistado (Líder SQA):** Lo que acordamos fue que el sistema funcionara sin errores graves, que la previsualización se viera bien en la pantalla de la tienda, y que el catálogo cargara completo. No hicimos pruebas formales con criterios medibles, pero más o menos eso era lo esperado.

### Pregunta B.5: ¿Se definió algún requisito no funcional específico?

**Entrevistado (Analista Técnico):** Solo que la aplicación corriera bien en las computadoras de la tienda, que eran equipos normales, no muy potentes. Y que cargara rápido, aunque nunca cuantificamos "rápido" con un número.

---

## Bloque C: Requisitos Nuevos y Scope Creep

### Pregunta C.1: ¿Cuándo surgieron los nuevos requerimientos?

**Entrevistado (Líder SQA):** Todoсуржио después de que pusimos el sistema en producción. Llevábamos como dos meses cuando Cliente empezó a platicar de "qué tal si...". Los primeros fueron los marcos dobles y el tipo de vidrio. Luego lo de multiples de las maria luisas y la pantalla secondaria.

### Pregunta C.2: ¿Quién solicitó los nuevos requerimientos?

**Entrevistado (Líder SQA):** Todo vino de Cliente, directo. No hubo intermediarios. En WhatsApp nos mandaba mensajes como "Oye, ¿y si le ponemos que el cliente pueda elegir si quiere vidrio normal o antirreflejo?".

### Pregunta C.3: ¿Pasaron por algún proceso formal de aprobación?

**Entrevistado (Líder SQA):** No, y esa es nuestra falla. Absolutamente no hubo proceso formal. Llegaban las ideas y nosotros simplemente las implementábamos o intentábamos. No había registro, no había estimación de tiempo, no había approval del cliente por escrito. Solo conversaciones de WhatsApp.

### Pregunta C.4: ¿Se estimó el impacto en tiempo y costo?

**Entrevistado (Líder SQA):** Se hizo un estimado de costo y de tiempo de forma empirica, El coste viniendo de un aproximado de cuanto queria ganar en el mes y la renta en funcion de prima de mantenimiento

### Pregunta C.5: ¿El cliente aceptó formalmente los cambios?

**Entrevistado (Líder SQA):** No de manera formal. Le dijimos que implementaríamos esas cosas pero nunca hubo un documento donde firmara que estaba de acuerdo con el alcance y el costo adicional. Eso generó cierta confusión después, porque él pensaba que todo estaba incluido en la renta y nosotros considerábamos que eran Cambios nuevos con costo extra.

---

## Bloque D: Modelo de Negocio y Estructura de Costos

### Pregunta D.1: ¿Cuál fue el costo total acordado inicialmente?

**Entrevistado (Líder SQA):** $24,000 MXN por todo el desarrollo completo. Eso incluía:
- La aplicación web completa
- El escaneo de todos los marcos del catálogo
- La base de datos con el catálogo
- La capacitación para usar el sistema

No hubo desglose por escrito, pero eso era lo que estaba incluido.

### Pregunta D.2: ¿Se definió un costo recurrente?

**Entrevistado (Líder SQA):** Sí, acordamos $2,500 MXN mensuales por la renta del sistema. Eso incluía el hosting, el mantenimiento de la base de datos, y soporte básico si había algún problema. Él entendía eso como "renta del sistema".

### Pregunta D.3: ¿Los nuevos requerimientos implican costos adicionales?

**Entrevistado (Líder SQA):** Aún no se lo hemos cobrado formalmente. Los REQ-07 a REQ-10 representan trabajo adicional que no estaba en el acuerdo original. Ahorita estamos en ese proceso de estimar el costo y presentárselo formalmente, porque él sigue preguntando cuándo se.

### Pregunta D.4: ¿Existe un contrato formal?

**Entrevistado (Líder SQA):** No, no hay contrato. Todo fue verbal y de buena fe. Eso es otro problema que queremos resolver para proyectos futuros.

### Pregunta D.5: ¿Qué incluye exactamente el costo de $24,000 MXN?

**Entrevistado (Analista Técnico):** Básicamente todo lo que necesita para el sistema:
- Desarrollo de la aplicación web (frontend y backend)
- Programa JS para detección de ancho y generación de 3D
- Escaneo de ~200 marcos por semana durante 5 semanas (aproximadamente 1,000 marcos)
- Creación de la base de datos con todas las especificaciones
- Instalación y configuración inicial
- Una capacitación de uso para los empleados

---

## Bloque E: Arquitectura Técnica y Stack Tecnológico

### Pregunta E.1: ¿Cuál es el stack tecnológico completo?

**Entrevistado (Analista Técnico):** Usamos:
- **Frontend:** HTML5 con Bootstrap para el diseño responsive, CSS3 para estilos custom, JavaScript vanilla para la interacción
- **Backend:** JavaScript con Node.js, aunque después optimizamos algunas cosas
- **Base de datos:** PostgreSQL, bastante robusta y con buen rendimiento
- **Herramientas auxiliares:** Un programa en Python que desarrollé específicamente para procesar las imágenes de los marcos, detectar el ancho y generar los modelos 3D
- **Hosting:** Un VPS que contratamos, está funcional desde hace meses

### Pregunta E.2: ¿Por qué se eligió esta tecnología?

**Entrevistado (Analista Técnico):** Porque era lo que más conocía Líder SQA y lo que funcionaba para este tipo de aplicación web. Era rápido de desarrollar y mantenible. Investigué alternativas como motores de juegos 3D, pero eran muy extenso para lo que necesitábamos. Al final usamos una librería de rendering 3D en JavaScript que funcionó bien.

### Pregunta E.3: ¿El sistema tiene una API?

**Entrevistado (Analista Técnico):** Tiene endpoints internos, pero no está diseñado como una API pública. Todo comunica internamente. Si Cliente quiere integrar con su sistema de ventas en el futuro, sí sería necesario exponer una API.

### Pregunta E.4: ¿Dónde está hosteado el sistema?

**Entrevistado (Analista Técnico):** En un VPS de un proveedor que nos dio Líder SQA. Tiene buenas reseñas y el precio era razonable. El dominio apunta a la aplicación y tiene SSL configurado.

### Pregunta E.5: ¿Cuál es el proceso de despliegue?

**Entrevistado (Analista Técnico):** Actualmente es manual. Cuando hay cambios, subo el código al servidor, reinicio los servicios. No tenemos un pipeline de CI/CD todavía, aunque sería ideal implementarlo.

---

## Bloque F: Flujo de Trabajo y Procesos de Negocio

### Pregunta F.1: ¿Cómo es el flujo típico de un cliente en la tienda?

**Entrevistado (Líder SQA):** El flujo actual es:
1. El cliente llega a la tienda con su foto (ya sea impresa o en el celular)
2. El empleado abre la aplicación web en la computadora de la tienda
3. El cliente sube su foto usando la opción de subir archivo o conectando el celular
4. El operador selecciona el marco y la maría Luisa según la clave de cada uno
5. Selecciona un marco y el sistema muestra la previsualización 3D
6. El cliente puede cambiar de marco las veces que quiera hasta encontrar el que le gusta
7. Cuando decide, el empleado captura la configuración y genera la orden

### Pregunta F.2: ¿Quién opera el sistema?

**Entrevistado (Líder SQA):** Cliente y sus empleados. Son los que atienden en la tienda. Son capaces de manejarlo sin otra ayuda, aunque a veces nos llaman si algo no funciona.

### Pregunta F.3: ¿Cuántos marcos tiene el catálogo?

**Entrevistado (Analista Técnico):** actualmente tenemos alrededor de 1079 marcos en el catálogo. Todos fueron escaneados y sus características registradas: ancho, alto, tipo de moldura, color, textura.

### Pregunta F.4: ¿El sistema está integrado con algún otro sistema?

**Entrevistado (Analista Técnico):** No, actualmente es unico. No se integra con su sistema de ventas ni con inventario. Es algo que Cliente mencionó que gustaría tener en el futuro.

### Pregunta F.5: ¿Hay algún proceso de mantenimiento?

**Entrevistado (Líder SQA):** Lo básico: respaldos semanales de la base de datos, actualizaciones de seguridad cuando hay parches. Pero no hay un mantenimiento preventivo formal. Si algo se rompe, lo arreglamos.

---

## Bloque G: Calidad y Expectativas

### Pregunta G.1: ¿Qué define como un "sistema exitoso"?

**Entrevistado (Líder SQA):** Que los clientes de Enmarcame queden satisfechos con lo que ven, los clientes puedan visualizar el resultado antes de comprar. Que no se caiga, que sea confiable.

### Pregunta G.2: ¿Ha tenido problemas con el sistema?

**Entrevistado (Líder SQA):** Algunos problemas menores: la aplicación se trababa con ciertas fotos de alta resolución, tuvimos que agregar compresión. Algunos marcos no renderizaban bien. Cosas así que fuimos corrigiendo sobre la marcha.

### Pregunta G.3: ¿Qué tan importante es el rendimiento?

**Entrevistado (Líder SQA):** Muy importante. Los clientes no quieren esperar. Tiene que ser rápido, casi instantáneo, que el tiempo de carga de 2-3 segundos, que era aceptable.

### Pregunta G.4: ¿El cliente ha solicitado funcionalidades de reporte?

**Entrevistado (Líder SQA):** No aún, pero sospecho que en el future podría pedir algo así. Le interesaría saber qué marcos son más populares, cuáles selecciona la gente, etc.

### Pregunta G.5: ¿Hay alguna expectativa de disponibilidad?

**Entrevistado (Líder SQA):** Básico: que el sistema funcione durante el horario de la tienda, que no haya caídas en horario de atención. No tiene 24/7, solo mientras está abierta la tienda.

---

## Bloque H: Cambios Futuros y Roadmap

### Pregunta H.1: ¿El cliente ha mencionado características futuras?

**Entrevistado (Líder SQA):** Sí, ya platicamos de varias cosas:
- La pantalla secundaria para que el cliente vea la previsualización en una pantalla más grande mientras el empleado opera
- Integración con su sistema de POS
- Posibilidad de que los clientes hagan pedidos desde sus casas
- Un portal para clientes frecuentes

### Pregunta H.2: ¿Hay planes de expansión?

**Entrevistado (Líder SQA):** Cliente quiere expandir su sistema en otras tiendas o incluso hacer una especie de franquicia, pero de momento solo es su tienda. No hay planes concretos de expansión a corto plazo.

### Pregunta H.3: ¿Requiere integración con redes sociales?

**Entrevistado (Líder SQA):** Mencionó algo de poner un iPad en la tienda donde los clientes pudieran tomar su foto y compartir en redes sociales, pero no es algo formal aún.

### Pregunta H.4: ¿Existe fecha límite para los requerimientos pendientes?

**Entrevistado (Líder SQA):** Que el cambio que sea pronto, pero no hay una fecha concreta. Estamos en el proceso de estimar el trabajo y definir prioridades.

### Pregunta H.5: ¿Cuál es la prioridad de los REQ-07 a REQ-10?

**Entrevistado (Líder SQA):**
- **REQ-07 (Marcos Dobles):** Alta prioridad, Cliente tiene clientes que pidiendo mucho esto
- **REQ-08 (Tipos de Vidrio):** Media prioridad, funcionalidad funcional pero no crítica
- **REQ-09 (Maria Luisa):** Media prioridad, ya tiene algunos diseños escaneados
- **REQ-10 (Pantalla Secondary):** Baja prioridad por ahora, requiere inversión adicional en hardware

---

## Hallazgos Clave de la Entrevista

### Hallazgo 1: Falta de Documentación Formal
No existe un documento formal de propuesta, contrato, ni especificación de requisitos original. Todo quedó en acuerdos verbales.

### Hallazgo 2: Scope Creep Sin Proceso
Los nuevos requerimientos (REQ-07 a REQ-10) llegaron sin pasar por un proceso formal de control de cambios, lo que ha generado confusión en expectativas y costos.

### Hallazgo 3: Costo Inicial y Recurrente Definido
- Costo de desarrollo: $24,000 MXN
- Renta mensual: $2,500 MXN
- No hay contrato formal

### Hallazgo 4: Stack Tecnológico Definido
- Frontend: HTML5, Bootstrap, CSS, JS
- Backend: Node.js
- Base de datos: PostgreSQL
- Herramientas: Python para procesamiento de imágenes

### Hallazgo 5: Estado de Requerimientos
- REQ-01 a REQ-06: Implementados
- REQ-07 a REQ-10: Pendientes sin estimación formal

---

## Acciones de Seguimiento

1. **Formalizar los CR-01 a CR-04** con estimaciones de tiempo y costo
2. **Presentar al cliente** los costos adicionales de los nuevos requerimientos
3. **Crear documento de propuesta formal** para referencia futura
4. **Priorizar** los requerimientos pendientes con el cliente
5. **Establecer proceso de control de cambios** para el futuro

---

## Aprobacion

| Campo | Valor |
|-------|-------|
| Elaborado por | Analista Técnico |
| Fecha | 2026-03-23 |
| Estado | Completado |

---

*Referencias: [[01-Baseline/04-Guia_Entrevista_PO]], [[01-Baseline/02-Propuesta_Recuperada]], [[01-Baseline/03-Acuerdos_Cliente]]