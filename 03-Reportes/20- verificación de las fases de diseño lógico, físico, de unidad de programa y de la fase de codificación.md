---
tags:
  - SQA
  - testing
  - life-cycle
  - lewis
  - verificacion
aliases:
  - Verificacion Fases Diseno y Codificacion
tema: Conceptos Fundamentales de Calidad del Software
---

# Verificacion de las Fases de Diseno y Codificacion

> **Referencia:** Lewis, W. E. (2009). *Software Testing and Continuous Quality
> Improvement* (2nd ed.). USA: Auerbach Publications.
> Paginas cubiertos: 79 - 95.

---

## A. Verificacion de la Fase de Diseno Logico (p. 79)

La **fase de diseno logico** refina los requerimientos de negocio en
preparacion para la especificacion del sistema, la cual sera utilizada
durante el diseno fisico y la codificacion.

Su objetivo es traducir los requerimientos funcionales e informativos a
modelos concretos que sirvan como base estructural de la aplicacion.

> [!NOTE] Contexto PDCA
> Dentro del ciclo de mejora continua de Deming, esta fase representa
> la transicion entre el **Plan** (requerimientos) y el **Do**
> (diseno fisico/codificacion). La verificacion en este punto previene
> que defectos se propaguen hacia fases posteriores y mas costosas.

**Entradas de la fase:**
- Documento de requerimientos (aprobado y congelado)
- Especificaciones funcionales preliminares

**Salidas verificables:**
- Modelo de datos (Entity Relationship Diagram)
- Modelo de procesos (Process Decomposition Diagram)
- Matriz de enlace CRUD (Create, Read, Update, Delete)

---

## B. Modelo de Datos, Modelo de Proceso y Enlace (pp. 79-80)

La fase de diseno logico produce **tres entregables principales** que
deben ser verificados de forma conjunta e individual.

---

### B.1 Modelo de Datos (Entity Relationship Diagram)

Un **modelo de datos** es una representacion de la informacion
requerida por la aplicacion. Establece asociaciones entre personas,
lugares y cosas de importancia para el sistema.

| Componente    | Descripcion                                                                 |
| ------------- | --------------------------------------------------------------------------- |
| **Entidad**   | Persona, lugar, cosa o evento unico e identificable sobre el que se almacena data |
| **Atributo**  | Caracteristica que describe una entidad (ej. tamano, fecha, valor, direccion) |
| **Relacion**  | Asociacion entre dos o mas entidades                                        |

**Tipos de relaciones (cardinalidad):**

- **Uno a uno (1:1):** Un ocurrencia de una entidad se vincula con
  cero o una ocurrencia de otra entidad.
- **Uno a muchos (1:N):** Una ocurrencia de una entidad se vincula
  con cero o mas ocurrencias de otra entidad.
- **Muchos a muchos (M:N):** Muchas ocurrencias de una entidad se
  vinculan con muchas ocurrencias de otra entidad.

---

### B.2 Modelo de Proceso (Process Decomposition Diagram)

Un **proceso** es una actividad de negocio con sus entradas y salidas
asociadas. El modelo de proceso es una representacion grafica que
describe **que** hace el proceso, sin referir el por que, como ni cuando.

**Conceptos clave:**

- **Descomposicion de procesos:** Desglose de actividades en niveles
  de detalle sucesivos hasta llegar a procesos elementales.
- **Proceso elemental:** La unidad minima de actividad que tiene
  significado para el usuario.
- **Diagrama de flujo de datos (DFD):** Verifica la descomposicion;
  muestra procesos, accesos a almacenes de datos y flujos entrantes
  y salientes.

**Jerarquia del diagrama:**

Raiz (proceso inicial)  
└── Padre (nivel superior)  
└── Hijo (nivel inferior descompuesto)  
└── Proceso elemental


---

### B.3 Enlace: Matriz CRUD (Association Diagram)

La **matriz CRUD** (tambien llamada *process-data matrix*) vincula
los modelos de datos y procesos. Mapea cada proceso contra las
entidades, mostrando cuales procesos **C**rean, **R**leen,
**U**ctalizan o **D**eliminan instancias en cada entidad.

**Proposito del analisis del ciclo de vida de entidades:**

1. Verificar que existe un proceso que *crea* cada entidad.
   Si no existe, el proceso esta ausente y debe definirse.
2. Verificar que existen procesos que *actualizan*, *leen* y
   *eliminan* instancias.
   Si una entidad nunca es accedida, puede ser candidata a eliminarse.

> [!TIP] Aplicacion en pruebas
> La matriz CRUD se puede aplicar directamente como tecnica de prueba
> (CRUD Testing, Apendice G9 de Lewis) para detectar omisiones en
> el modelo logico antes de la codificacion.

---

## C. Prueba del Diseno Logico con Revisiones Tecnicas (pp. 80-81)

La fase de diseno logico se verifica con **tecnicas estaticas**
(no ejecucion de la aplicacion), identicas a las usadas en la
fase de requerimientos.

**Tecnicas estaticas aplicadas:**

- **Inspecciones y walkthroughs:** Evaluacion formal de forma,
  interfaces y restricciones de solucion del diseno.
- **Checklists:** Orientados al control de calidad; aseguran la
  completitud de los modelos.
- **Checklist metodologico:** Verifica que los pasos y tareas
  metodologicos se hayan seguido correctamente.

**Productos de trabajo a revisar:**
- Modelo de datos
- Modelo de procesos
- Matriz CRUD

**Registro de defectos del diseno logico:**

Cada defecto encontrado debe documentarse en un formulario de
reporte con las columnas: *Categoria de defecto*, *Faltante*,
*Incorrecto* y *Extra*.

| # | Categoria de Defecto                    |
|---|-----------------------------------------|
| 1 | Los datos no han sido adecuadamente definidos |
| 2 | Definicion de entidad incompleta        |
| 3 | Cardinalidad de entidad incorrecta      |
| 4 | Atributo de entidad incompleto          |
| 5 | Normalizacion violada                   |
| 6 | Llave primaria incorrecta               |
| 7 | Llave foranea incorrecta                |
| 8 | Llave compuesta incorrecta              |
| 9 | El proceso no ha sido adecuadamente definido |
| 10| Proceso padre incompleto               |

> [!WARNING] Resultado de la revision
> - **Sin problemas:** El diseno logico se congela.
> - **Problemas menores:** El autor corrige y el moderador valida.
> - **Problemas mayores:** Se corrigen defectos y se programa
>   una nueva revision con los mismos integrantes.

---

## D. Refinamiento del Plan de Prueba de Aceptacion/Sistema (pp. 81-82)

Durante la fase de requerimientos, no habia suficiente detalle para
definir todos los tipos de pruebas del sistema. El **diseno logico**
proporciona modelos de datos y procesos que permiten refinar
significativamente el plan de prueba.

**Actualizaciones al plan durante esta fase:**

### Seccion: Test Approach and Strategy
- Refinamiento del **alcance de pruebas** con base en los modelos
- Definicion detallada de **tipos de pruebas de sistema**:
  - Funcional
  - Rendimiento (Performance)
  - Seguridad
  - Usabilidad
  - Compatibilidad
- Refinamiento de enfoque de prueba, logistica y politica de regresion
- Inicio de: instalaciones de prueba, procedimientos, organizacion,
  librerias y herramientas de prueba

### Seccion: Test Execution Setup
- Sistema de prueba (process), instalacion, recursos, plan de
  herramientas y organizacion de pruebas

### Seccion: Test Specifications
- Se agregan detalles funcionales del modelo de datos y procesos
  a la **requirements-test matrix**
- Se **inicia** el diseno de casos de prueba de nivel sistema
- Los casos de prueba de **aceptacion** deben completarse en esta fase

### Seccion: Test Procedures
- Se refinan los elementos iniciados en la fase anterior

> [!NOTE] Nota importante
> Aun es demasiado temprano para completar el desarrollo detallado
> de pruebas (ej. procedimientos de prueba, scripts y valores de
> entrada/salida). Eso corresponde a fases posteriores.

---

## E. Verificacion de la Fase de Diseno Fisico (p. 83)

La **fase de diseno fisico** determina *como* los requerimientos
pueden ser automatizados. Crea un diseno de alto nivel donde se
definen los componentes procedurales basicos, sus interrelaciones
y las principales representaciones de datos.

**Diferencia clave con el diseno logico:**

| Aspecto             | Diseno Logico        | Diseno Fisico           |
|---------------------|----------------------|-------------------------|
| Enfoque             | Funcional            | Estructural             |
| Objetivo            | Que hace el sistema  | Como se construye       |
| Tecnicas            | ERD, DFD, CRUD       | Structure charts, WarnierOrr, Jackson |
| Verificacion        | Correccion funcional | Integridad del diseno   |

> [!INFO] Premisa de la fase
> El diseno fisico **asume** que los requerimientos y el diseno
> logico son correctos; se concentra exclusivamente en la
> integridad estructural del diseno mismo.

**Esquemas de representacion de diseno fisico:**
- **Structure Charts** (Yourdon)
- **Diagramas de WarnierOrr**
- **Diagramas de Jackson**
- **Diagramas de navegacion de datos**
- **Diagramas de base de datos relacionales** (mapeados desde el
  diseno logico)

---

## F. Prueba del Diseno Fisico con Revisiones Tecnicas (pp. 83-84)

Al igual que las fases previas, el diseno fisico se verifica con
**tecnicas estaticas** enfocadas en la arquitectura del diseno.

**Tipos de errores que detecta el analisis estatico:**

- **Errores de control de flujo:** Un modulo puede necesitar un
  dato que otro crea pero no proporciona correctamente.
- **Errores estaticos y semanticos:** Relacionados con descomposicion
  de datos, descomposicion funcional y flujo de control.

**Concepto clave - Acoplamiento (Coupling):**

El **acoplamiento** mide el grado de independencia entre modulos.

| Tipo de Acoplamiento | Descripcion                                                   | Calidad     |
|----------------------|---------------------------------------------------------------|-------------|
| **Acoplamiento de datos** | Dos modulos se comunican via variable o arreglo pasado como parametro | Bueno |
| **Acoplamiento de control** | Un modulo controla la logica de otro             | Regular     |
| **Acoplamiento de contenido** | Un modulo refiere o modifica los internos de otro | Malo   |

> [!TIP] Principio de diseno
> El **acoplamiento debil (loose coupling)** es considerado una
> buena practica de diseno. El analisis estatico puede determinar
> la presencia o ausencia de acoplamiento en los esquemas de diseno.

**Registro de defectos del diseno fisico:**

| # | Categoria de Defecto                                        |
|---|-------------------------------------------------------------|
| 1 | Logica o secuenciacion erronea                              |
| 2 | Procesamiento impreciso                                     |
| 3 | La rutina no tiene entrada/salida de parametros requeridos  |
| 4 | La rutina no acepta todos los datos en el rango permitido   |
| 5 | Verificaciones de limite y validez no implementadas         |
| 6 | Procedimientos de recuperacion no implementados o inadecuados |
| 7 | Procesamiento requerido faltante o inadecuado               |
| 8 | Valores erroneos o ambiguos                                 |
| 9 | Almacenamiento de datos erroneo o inadecuado                |
| 10| Variables faltantes                                         |

---

## G. Creacion de Casos de Prueba de Integracion (p. 85)

La **prueba de integracion** esta disenada para probar la estructura
y la arquitectura del software, verificando si todos los componentes
se interfazan correctamente.

> [!IMPORTANT] Definicion
> La prueba de integracion es el proceso de identificar errores
> introducidos al **combinar modulos** de programa unitariamente
> probados. **No** verifica correccion funcional del sistema;
> solo verifica que los modulos se integren correctamente.

**Condiciones previas:**
- No debe comenzar hasta que se confirme que **todas las unidades**
  se desempenan segun sus especificaciones.

**Tecnicas de prueba de integracion:**
- **Top-down:** Se integra de arriba hacia abajo en la jerarquia
- **Bottom-up:** Se integra de abajo hacia arriba
- **Sandwich testing:** Combinacion de top-down y bottom-up
- **Thread testing:** Prueba de hilos de funcionalidad especificos

---

## H. Metodologia para Pruebas de Integracion (pp. 85-86)

Lewis describe una metodologia de 4 pasos para crear casos
de prueba de integracion:

### Paso 1: Identificar Interfaces de Unidad

El desarrollador de cada unidad de programa identifica y documenta
las interfaces de la unidad para las siguientes operaciones:

| Operacion de Interfaz    | Descripcion                                              |
|--------------------------|----------------------------------------------------------|
| **Consulta externa**     | Responder a consultas de terminales para informacion     |
| **Entrada externa**      | Gestionar datos de transaccion ingresados para procesamiento |
| **Archivo externo**      | Obtener, actualizar o crear transacciones en archivos    |
| **Archivo interno**      | Pasar o recibir informacion de otras unidades logicas    |
| **Despliegue externo**   | Enviar mensajes a terminales                             |
| **Salida externa**       | Proveer resultados de procesamiento a dispositivos de salida |

### Paso 2: Reconciliar Interfaces por Completitud

Se recolecta la informacion del **template de prueba de integracion**
para todas las unidades. Cuando una unidad tiene interfaz con otra,
se verifica que la salida de una sea registrada como entrada de la otra.

### Paso 3: Crear Condiciones de Prueba de Integracion

Se preparan una o mas condiciones de prueba para integrar
cada unidad de programa. El numero de condicion se documenta
en el template de integracion.

### Paso 4: Evaluar Completitud de Condiciones

**Preguntas guia para evaluar completitud:**

- [ ] Se desarrollo una prueba de integracion para cada consulta
      externa (record test, file test, search test, match-merge test,
      attributes test, stress test, control test)?
- [ ] Se validan todas las interfaces entre modulos (salida de uno =
      entrada de otro)?
- [ ] Se valido el procesamiento de cada unidad antes de la integracion?
- [ ] Todos los desarrolladores de unidades acuerdan que las
      condiciones son adecuadas?
- [ ] Todas las unidades de software estan incluidas?
- [ ] Todos los archivos usados estan incluidos?
- [ ] Todas las transacciones de negocio asociadas estan incluidas?
- [ ] Todas las funciones de terminal estan incluidas?

> [!NOTE] Documentacion
> Los casos de prueba de integracion se documentan en la seccion
> **Test Specifications** del plan de prueba del sistema/aceptacion
> (Apendice E2 de Lewis). Los casos de prueba del sistema deben
> completarse durante esta fase.

---

## I. Verificacion de la Fase de Diseno de la Unidad del Programa (p. 87)

La **fase de diseno de la unidad del programa** (Program Unit Design)
es el **diseno detallado** en el que se realizan elecciones especificas
de algoritmos y estructuras de datos. Especifica el flujo detallado
de control que sera facilmente traducible a codigo fuente.

> [!INFO] Objetivo
> Un buen diseno detallado es aquel que puede traducirse facilmente
> a multiples lenguajes de programacion.

---

## J. Prueba del Diseno de la Unidad del Programa con Revisiones Tecnicas (pp. 87-88)

Esta fase se verifica usando **tecnicas estructuradas** que analizan
los constructos de programacion antes de la codificacion.

**Constructos de programacion estructurada verificados:**

| Constructo    | Descripcion                                                                | Ejemplo        |
|---------------|----------------------------------------------------------------------------|----------------|
| **Secuencia** | Sentencias ejecutadas una tras otra en el orden que aparecen              | Asignaciones   |
| **Seleccion** | Condicion probada; se ejecuta una de dos rutas alternativas               | if-then-else   |
| **Iteracion** | Conjunto de instrucciones ejecutado un numero de veces mediante un bucle  | do-until, do-while |

**Tipos de bucles:**
- **do-until:** Ejecuta instrucciones y *luego* prueba la condicion
  de terminacion. Si es verdadera, el bucle termina.
- **do-while:** Prueba la condicion de terminacion *primero*. Si es
  verdadera, pasa al siguiente constructo; si es falsa, ejecuta las
  instrucciones de nuevo.

> [!WARNING] Errores detectables
> El analisis estatico del diseno detallado detecta errores semanticos
> que involucran **flujo de informacion** y **flujo de control logico**.

**Registro de defectos del diseno de unidad:**

| # | Categoria de Defecto                         |
|---|----------------------------------------------|
| 1 | Constructo if-then-else usado incorrectamente |
| 2 | Constructo do-while usado incorrectamente    |
| 3 | Constructo do-until usado incorrectamente    |
| 4 | Constructo case usado incorrectamente        |
| 5 | Existen bucles infinitos                     |
| 6 | No es un programa propio                     |
| 7 | Existen sentencias goto                      |
| 8 | El programa no es legible                    |
| 9 | El programa no es eficiente                  |
| 10| El constructo case no contiene todas las condiciones |

---

## K. Creacion de Casos de Prueba de la Unidad (pp. 88-89)

La **prueba unitaria** es el proceso de ejecutar un subconjunto
funcional del sistema para determinar si realiza su funcion asignada.
Esta orientada a verificar una funcion o modulo especifico.

**Tipos de casos de prueba unitaria:**

| Tipo        | Proposito                                                     |
|-------------|---------------------------------------------------------------|
| **White-box** | Valida la logica interna de la unidad (rutas de codigo)    |
| **Black-box** | Prueba la unidad contra sus especificaciones (comportamiento externo) |

**Concepto de cobertura de codigo:**

Durante el desarrollo de casos de prueba unitaria es fundamental
conocer que porciones del codigo han sido sometidas a prueba y
cuales no. La cobertura inadequada es un riesgo de calidad porque
pueden existir defectos en las porciones no probadas.

> [!NOTE] Automatizacion
> La prueba unitaria facilita la automatizacion porque los
> comportamientos de unidades pequenas pueden ser capturados
> y reproducidos con maxima reutilizabilidad.

**Estado del plan de prueba al final de esta fase:**

- **Test Specifications:** Se inician los casos de prueba unitaria
- **Introduction, Test Approach & Strategy, Test Execution Setup,
  Test Tools, Personnel Resources:** Deben estar completos
- **Functional decomposition, integration, system y acceptance
  test cases:** Deben estar completados
- **Test Procedures y Test Schedule:** Continuan en refinamiento

---

## L. Verificacion de la Fase de Codificacion (p. 91)

La **fase de codificacion** es la traduccion del diseno detallado
a codigo ejecutable usando un lenguaje de programacion.

La base de una buena programacion son los **estandares de programacion**
previamente definidos. Estos deben incluir:

| Estandar                       | Descripcion                                                   |
|--------------------------------|---------------------------------------------------------------|
| **Comentarios**                | Como y en que nivel debe comentarse el programa               |
| **Construcciones inseguras**   | Practicas que dificultan el mantenimiento (ej. sentencias goto) |
| **Layout del programa**        | Disposicion estandar en pagina, indentacion de constructos    |
| **Programacion defensiva**     | Manejo de condiciones de error y control a rutina de errores  |

---

## M. Prueba de Codificacion con Revisiones Tecnicas (p. 91)

Las **tecnicas de analisis estatico** (walkthroughs estructurados e
inspecciones) se usan para asegurar la forma correcta del codigo
fuente y la documentacion.

**Objetivos de la revision:**
- Verificar adherencia a convenciones de codificacion y documentacion
- Verificacion de tipos (type checking)
- Detectar defectos antes de la ejecucion

**Registro de defectos de la fase de codificacion:**

| # | Categoria de Defecto                                       |
|---|------------------------------------------------------------|
| 1 | Logica de decision o secuenciacion erronea o inadecuada    |
| 2 | Computos aritmeticos erroneos o inadecuados                |
| 3 | Ramificacion (branching) erronea                           |
| 4 | Ramificacion u otras pruebas realizadas incorrectamente    |
| 5 | Existen terminaciones de bucle no definidas                |
| 6 | Reglas del lenguaje de programacion violadas               |
| 7 | Estandares de programacion violados                        |
| 8 | El programador malinterpreta constructos del lenguaje      |
| 9 | Existen errores tipograficos                               |

---

## N. Ejecucion del Plan de Prueba (pp. 91-92)

Al final de la fase de codificacion, todos los elementos del
plan de prueba deben estar completados. La **prueba dinamica**
(ejecucion real del software) procede en **orden inverso** al
ciclo de desarrollo:

Codificacion → Prueba Unitaria → Prueba de Integracion  
→ Prueba de Sistema → Prueba de Aceptacion


> [!INFO] Prueba estatica vs. dinamica
> - **Prueba estatica:** Revision manual de resultados especificados
>   en casos de prueba y procedimientos. Asegura correccion desde
>   un punto de vista no ejecutable.
> - **Prueba dinamica:** Tecnicas dependientes del tiempo que implican
>   ejecutar una secuencia especifica de instrucciones con el
>   computador para estudiar la correccion funcional y computacional.

---

## O. Prueba Unitaria (pp. 92-93)

La **prueba unitaria** es el nivel basico de prueba. Se enfoca
separadamente en los bloques constructivos mas pequenos de un
programa o sistema.

**Definicion:** Proceso de ejecutar cada modulo para confirmar
que cada uno realiza su funcion asignada.

**Ventajas:**

- Permite probar y depurar unidades pequenas, facilitando la
  integracion posterior.
- Hace matematicamente posible probar completamente la logica
  del codigo con menos pruebas.
- Facilita la **automatizacion de pruebas** porque el comportamiento
  de unidades pequenas puede capturarse y reproducirse con
  maxima reutilizabilidad.

**Tipos de unidades:**
- El modulo en si mismo
- Componentes GUI (ventanas, menus, funciones)
- Programas batch
- Programas en linea (online)
- Procedimientos almacenados (stored procedures)

---

## P. Prueba de Integracion (p. 93)

Despues de la prueba unitaria, todos los modulos deben ser
probados en integracion.

**Proceso:**

> El sistema se construye lentamente agregando uno o mas modulos
> a la vez al nucleo de modulos ya integrados.

**Principios:**
- Porque los modulos han sido probados unitariamente previamente,
  pueden tratarse como **cajas negras (black-boxes)**.
- La integracion se concentra en las **interfaces entre modulos**.
- Se usa **prueba incremental:** en cada paso se agrega un modulo,
  se prueba hasta que funcione correctamente, y luego se agrega otro.

**Metas:**
1. Verificar que cada modulo se desempena correctamente dentro
   de la estructura de control.
2. Verificar que las interfaces entre modulos son correctas.

---

## Q. Prueba del Sistema (pp. 93-94)

Despues de la prueba de integracion, el sistema se prueba
**como un todo** para funcionalidad y aptitud de uso (*fitness
of use*), basado en el plan de prueba del sistema/aceptacion.

**Enfoque de prueba:**

| Tipo        | Descripcion                                                   |
|-------------|---------------------------------------------------------------|
| **Black-box** | Prueba la funcionalidad del programa contra sus especificaciones |
| **White-box** | Prueba rutas de logica para verificar resultados predecibles |
| **Gray-box**  | Combinacion de ambos; enfoque balanceado ampliamente usado en sistema |

**Tipos de pruebas de sistema (atributos de calidad):**

- Prueba funcional
- Prueba de rendimiento (performance)
- Prueba de estres (stress)
- Prueba de compatibilidad
- Prueba de usabilidad
- Prueba de conversion
- Prueba de documentacion

> [!NOTE] Fuente de las pruebas
> Las fuentes de las pruebas de sistema son los **atributos de calidad**
> especificados en el plan de aseguramiento de calidad del software
> (SQAP). Aseguran que la prueba de aceptacion ocurra sin mayores problemas.

---

## R. Prueba de Aceptacion (p. 94)

La **prueba de aceptacion** certifica que el sistema software
satisface los requerimientos originales del usuario.

> [!IMPORTANT] Precondicion
> Esta prueba **no debe realizarse** hasta que el software haya
> completado exitosamente la prueba de sistema.

**Caracteristicas:**

- Es una prueba **ejecutada por el usuario final** (user-run test).
- Usa tecnicas de **caja negra (black-box)** para probar el sistema
  contra sus especificaciones.
- Los usuarios finales son responsables de asegurar que toda la
  funcionalidad relevante haya sido probada.
- La prueba continua incluso cuando se encuentran errores, a menos
  que el error en si impida la continuacion.

**Procedimiento:**
El plan de prueba de aceptacion define los procedimientos para ejecutar
las pruebas y debe seguirse tan fielmente como sea posible.

> [!NOTE] Casos especiales
> Algunos proyectos no requieren prueba de aceptacion formal cuando
> el cliente o usuario esta satisfecho con las otras pruebas realizadas.
> En esos casos, la prueba de sistema puede servir como prueba de
> aceptacion.

---

## S. Registro de Defectos (p. 95)

Cada defecto descubierto durante las pruebas debe documentarse
en un **reporte de problema (Problem Report)**.

**Cuando se genera un reporte de problema:**

> Un reporte de problema se genera cuando un procedimiento de prueba
> da lugar a un evento que no puede ser explicado por el tester.

**Contenido minimo del reporte de problema:**

| Campo                | Descripcion                                        |
|----------------------|----------------------------------------------------|
| Problem Identification | Identificador unico del problema                |
| Author               | Quien reporto el defecto                           |
| Release/Build Number | Version del software donde se encontro             |
| Open Date            | Fecha de apertura del reporte                      |
| Close Date           | Fecha de cierre/resolucion                         |
| Problem Area         | Area del sistema afectada                          |
| Defect or Enhancement| Clasificacion del hallazgo                         |
| Test Environment     | Ambiente donde se encontro el defecto              |
| Defect Type          | Tipo de defecto                                    |
| Who Detected         | Quien detecto el problema                          |
| How Detected         | Como fue detectado                                 |
| Assigned to          | A quien se asigno la correccion                    |
| Priority             | Prioridad de resolucion                            |
| Severity             | Severidad del impacto                              |
| Status               | Estado actual del reporte                          |

**Otros reportes de prueba complementarios:**

| Reporte                        | Proposito                                                |
|--------------------------------|----------------------------------------------------------|
| **Test Case Log**              | Documenta casos de prueba ejecutados y sus resultados    |
| **Test Log Summary Report**    | Documenta casos de los logs del tester para reporte de estado y recoleccion de metricas |
| **System Summary Report**      | Preparado para cada evento mayor de prueba; resume todas las pruebas |

---

## Resumen Visual del Ciclo de Vida de Pruebas

Requerimientos --> Construir Plan Prueba Sistema/Aceptacion  
+ Revisiones tecnicas de requerimientos

Diseno Logico --> Refinamiento del Plan + Rev. Tecnicas  
+ Diseno de casos prueba de aceptacion

Diseno Fisico --> Casos de prueba de integracion  
+ Rev. Tecnicas de diseno fisico

Diseno Unidad Programa --> Casos de prueba unitaria  
+ Rev. Tecnicas de diseno de unidad

Codificacion --> Ejecucion de pruebas:  
Unit Testing  
Integration Testing  
System Testing  
Acceptance Testing  
+ Registro de defectos

 Referencias - Lewis, W. E. (2009). *Software Testing and Continuous Quality   Improvement* (2nd ed.). USA: Auerbach Publications. pp. 79-95.`

---