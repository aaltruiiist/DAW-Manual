## Sistema de control de versiones 
Git es un sistema  de control de versiones. Este sistema permite realizar un seguimiento,una gestión y una revisión de todos los cambios de código de un software a lo largo del tiempo. 

Este sistema es fundamental para tener flujos de trabajo eficientes, permitiendo la contribución a una base de código compartida de forma independiente.

El sistema de control de versiones también actúa como un mecanismo de seguridad, permitiendo deshacer actualizaciones de código si ocurriese un error.

## Conceptos básicos
Antes de explicar el funcionamiento es preciso comentar algunos conceptos básicos:

Directorio
: Carpeta que contiene una copia de una versión concreta del proyecto con la que se está trabajando.

Staging area 
: Zona donde se guardan los cambios temporalmente desde el directorio de trabajo antes de hacerlos definitivos y registrarlos en el repositorio.

Repositorio
: Todo proyecto que está siendo seguido por GIT, el cual contiene un historial en el que se están registrando los cambios confirmados desde la zona temporal (staging area).

Ramas
: El proyecto puede contener varias bifurcaciones del estado del código, que sirven como nuevos camino para evolucionar el código, en paralelo con otras ramas. 

Clon
: Copia exacta del repositorio. Es lo primero que debe hacer un programador cuando se integra al equipo. Cada miembro de un grupo de trabajo tiene un clon del repositorio en su equipo local.

## Funcionamiento de Git

Git maneja los datos como una secuencia de copias instantáneas.

Tiene tres estados principales en los que se pueden encontrar los archivos:

**Confirmado:** Los datos están almacenados en la base de datos local.

**Modificado:** El archivo ha sido modificado, pero los cambios no se han confirmado a la base de datos.

**Preparado:** Se ha marcado un archivo previamente modificado para ser confirmado.
Por lo tanto, Git tiene tres secciones principales dentro de un proyecto:

**El directorio de Git:** Es lo que se copia cuando clonas un repositorio desde otro ordenador. Dentro se almacenan los metadatos y la base de datos de objetos.

**El directorio de trabajo:** Es una copia de una versión del proyecto. Se sacan de la base de datos y se colocan en el disco del ordenador para ser usados y modificados.

**El área de preparación:** Archivo que almacena información acerca de los cambios que vamos a confirmar en nuestra próxima confirmación.

Lo que hemos explicado hasta aquí se denomina flujo de trabajo, que se resume en los siguientes pasos:
1. Modificamos una serie de archivos en el directorio de trabajo.
2. Preparamos los archivos que queramos confirmar en el área de preparación.
3. Confirmamos los cambios, tomando los archivos del área de preparación y almacenando una copia instantánea de manera en el directorio de Git. 

La estructura de un directorio .git contiene:

**Carpeta objects/:** Directorio en el que se almacenan los contenidos de los archivos insertados, los commits, los árboles (crean la jerarquía entre archivos para un repositorio) y etiquetas de objeto (las etiquetas son como una cadena arbitraria que apunta a un commit específico, es nombre que se puede usar para marcar un punto específico en el historial de un repositorio).

**carpetas objects/[0-9a-f][0-9a-f]:** Un objeto recién creado se almacena en su propio archivo.

**Carpeta objects/pack:** Directorio con archivos que almacenan muchos objetos de forma comprimida, junto con     archivos index para partmitir el acceso aleatorio a ellos.

**Carpeta objects/info:** Directorio con información adicional sobre el objeto almacenado.

**Carpeta refs/:** En los subdirectorios se almacenan referencias.

**Carpeta refs/heads/:** Contiene objetos commit.

**Carpeta refs/tags/:** Contiene cualquier nombre de objeto.

**Carpeta refs/remotes/:** Contiene objetos commit de ramas copiadas de un repositorio remoto.

**Archivo packed-refs:** Es útil para un acceso eficiente al repositorio.

**Archivo HEAD:** Referencia simbólica a la rama en donde nos encontramos en cada momento.

**Archivo config:** Mantiene las opciones de Git específicas para el proyecto.

**Carpeta hooks:** Contiene scripts de shell que se ejecutan después de ejecutar los comandos Git.

**Archivo index:** Área de preparación entre el directorio de trabajo y el repositorio. Se pueden crear un conjunto de cambios que se deseen guardar juntos.

**Carpeta logs:** Almacena los cambios realizados en refs en el repositorio.

**Carpeta modules:** Contiene repositorios git de los submódulos.

**Carpeta worktrees:** Tienen los datos administrativos de árboles de trabajo vinculados.


## Git como la mejor alternativa
Que ventajas aporta frente a otros sistemas de versiones.
**1. La capacidad de ramificación:** Cuando un desarrollador quiere desarrollar algo específico sobre su proyecto, crea una nueva rama para garantizar que la rama principal siempre contenga el código depurado y de calidad para la producción. 

**2. Es un sistema de control de versiones distribuído:** Cada integrante del proyecto tiene su repositorio local, con unhistorial completo de confirmaciones. No hay riesgo de que alguien rompa la cadena de producción.

**3. Solicitudes de extracción:** Es una forma de solicitar a un desarrollador que fusione una de sus ramas en su repositorio. Facilita realizar un seguimiento de los cambios antes de integrarlos a la base de código.

**4. Comunidad:** Al ser muy popular, es fácil aprovechar las bibliotecas de terceros.

**5. Ciclo de liberación:** Las características de Git facilitan el flujo de trabajo y hacen que sea más ágil y veloz. 

## Distintos tipos de clientes

### Clientes Git para Linux
1. QGit: Muestra gráficamente ramas y permite ver los cambios en los archivos, los árbloes, historiales de archivos, revisiones y diferencias.
2. Gitg: Permite realizar operaciones Git comunes, revisar confirmaciones y obtener una vista previa de los archivos. Se puede además ver mensajes de confirmación. 
Los archivos grandes suelen cargarse más lentamente y no muestran el historial.

