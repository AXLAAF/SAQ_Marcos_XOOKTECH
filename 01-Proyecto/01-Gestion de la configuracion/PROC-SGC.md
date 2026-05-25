# Proceso de Gestión del Repositorio Documental (Obsidian + Relay)
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Estándares ETVX y Gobernanza
**Salidas:** Vault de Obsidian Auditado y Coherente

---

## Propósito

Éste propósito describe la creación, configuración del vault compartido en Obsdian utilizando el plugin Relay para la sincronización. Toda la documentación del proyecto (requisitos, actas, diseños, etc.) se almacenará y versionará en este vault. Ésto asegura que los miembros del equipo tengan acceso a la misma versión de los documentos.

## Alcance

Aplica a todo el ciclo de vida del proyecto "Visualizador de marcos". Cubre desde la instalación de Obsidian hasta las operaciones diarias: creación de carpetas, nombramiento de archivos, sincronización, respaldo y resolución de conflictos.

## Proceso
### Paso 1. Instalación de Obsidian

1.  Cada miembro debe descargar Obsidian desde su sitio oficial: https://obsidian.md.
2. Instalar el programa según el sistema operativo (la página suele detectar el SO).
(Imágen del proceso de instalación)

### Paso 2. Creación del vault local (por el Líder del Proyecto)

1. El líder del proyecto abre Obsidian y hace clic en "Crear nuevo Vault".
	*(Captura de pantalla: Crear nuevo Vault en Obsidian)*
2. Asigna el nombre del proyecto: `Visualizador-Marcos`.
	*(Captura de pantalla: Asignación de Nombre del Proyecto)*
3. Elige una ubicación en su disco duro.
	*(Captura de pantalla: Elección de ubicación en disco)*
4. Hace clic en "Crear". El vault se abrirá automáticamente.
### Paso 3. Instalación del plugin Relay

1. En Obsidian, presionar el botón de ajustes (icono con forma de tuerca).
	*(Captura de pantalla: Configuración / Icono de Ajustes)*
2. Seleccionar la pestaña "Complementos comunitarios" y presionar el botón de "Activar complementos creados por la comunidad".
	*(Captura de pantalla: Activación de complementos comunitarios)*
3. Ahora saldrá una sección de "Complementos creados con la comunidad", presionar el botón de "Buscar".
	*(Captura de pantalla: Botón de buscar complementos comunitarios)*
4. En el buscador, escribir "Relay", localizar el plugin y darle clic.
	*(Captura de pantalla: Búsqueda y localización del plugin Relay)*
5. Dar clic a "Instalar".
	*(Captura de pantalla: Botón de Instalar plugin)*
6. Después de instalarlo, dar clic a "Activar".
	*(Captura de pantalla: Botón de Activar plugin)*
*Mejora sugerida: Instalar también el plugin "**Obsidian Git**" como respaldo opcional, aunque Relay será el principal.*

### Paso 4. Configuración del servidor Relay.