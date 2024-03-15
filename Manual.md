
## Comandos de Git

### Comandos básicos de Git

**git init:** Crea un nuevo repositorio local, si no se le especifica una ruta, lo creará en el directorio actual, sinó en la ruta especificada.
    
    git init [nombre del proyecto]


**git clone:** Comando que permite clonar el codigo fuente de la ultima version de un repositorio ya sea remoto o local.

- Remoto: 
  
        git clone nombredeusuario@host:/ruta/al/repositorio
- Local: 
  
        git clone /ruta/al/repositorio

<br>

**git add:** Sirve para añadir archivos, el siguiente ejemplo añade un archivo txt.

     git add <ejemplo.txt>

<br>    

**git commit:** Crea una instantánea de los cambios actuales y los guarda en el directorio git.

    git commit -m "Mensaje que acompaña al commit"

<br>

**git config:**  Se utiliza para establecer la configuracion de usuario, como el email, nombre de usuario y formato

    git config --global user.email ejemplo@ejemplo.com

La propiedad --global configura ese correo para todos los repositorios locales. Por otro lado si necesitas utilizar diferentes correos puedes utilizar el siguiente parametro:
    
    git config --local user.email ejemplo@ejemplo.com
<br>

**git status:** Muestra la lista de los archivos que se han modificado y que estan preparados o confirmados:

    git status

<br>

**git push:** Sirve para confirmar los cambios locales a la rama del repositorio remoto.

    git push origin <nombre de la rama>

<br>

**git checkout:** Sirve para la navegacion entre ramas y la creacion de las mismas.

- Crea una rama y se mueve directamente a ella:
    
        git checkout -b <nombredelarama>

<br>

- Cambia la rama actual:
        
        git checkout <nombredelarama>

<br>

- Restaura un archivo borrado anteriormente
        
        git checkout -- ejemplo.txt

 Desde la versión 2.23 tenemos dos nuevos comandos que hacen la funcion del  comando checkout, con la intencion de reducir el uso del mismo, ya que se encargaba varias funcionalidades diferentes.

**git switch:**
- Crea una rama y se mueve directamente a ella:
    
        git switch -c <nombredelarama>

- Cambia la rama actual:
        
        git switch <nombredelarama>

**git restore:** 

Restaura un archivo que haya sido borrado anteriormente
  
    git restore ejemplo.txt

<br>

**git remote:**  Visualiza todos los repositorios remotos.

- Lista todos las conexiones con sus respectivas URLs:

        git remote -v

- Conecta el repositorio local a un servidor remoto

        git remote add origin <path/url>

- Elimina una conexion a un repositorio remoto:

        git remote <nombredelrepositorio>

<br>

**git branch:** Se usa para listar todas las ramas del repositorio.

        git branch


<br>

**git pull:** Sincroniza los cambios del repositorio remoto con tu directorio local.

        git pull


<br>

**git merge:** Se usa para fusionar una rama con otra rama activa.

        git merge <nombrelarama>


<br>

**git diff:** Se usa para listar los conflictos respecto a un archivo base.

        git diff --base <nombrearchivo>

- Ver los conflictos entre ramas antes de fusionarlas:

        git diff <ramaorigen> <ramaobjetivo>

- Para ver todos los conflictos presente se utiliza:
  
        git diff


<br>

**git tag:** Marca commmits especificos.

        git tag 1.1.0 <id-commit>
        
<br>

**git log:** Se utiliza para ver el historial del repositorio listando algunos detalles:

<br>

**git rm:** Se utiliza para borrar archivos del directorio de trabajo

        git rm archivo.txt

<br>

**git show:** Muestra informacion sobre cualquier objeto de git


### Comandos avanzados

**git stash:** Guarda momentáneamente los cambios que no estan listos para ser confirmados. De esta forma puedes volver al proyecto más tarde.

        git stash

- *git stash save*: Almacena tus cambios en un stash y añade un nombre descriptivo.
        
        git stash save "Montando el entorno de test"

- *git stash list*: Lista todos los stash.

        git stash list

- *git stash pop*: Recuperar el último stash.
        
        git stash pop

- *git stash pop --index*: Recuperar un stash concreto.
        
        git stash pop --index 2

- *git stash branch*: Crear una rama con los cambios que tienes

        git stash branch F/branch-name.

- *git stash clear*: Eliminar los stashes.

        git stash clear

- *git stash -p*: Almacenar en un stash sólo algunos archivos
        
        git stash -p
<br>

**git cherry-pick:** Se utiliza para aplicar el commit de una rama en otra.


- *git cherry-pick <commit>*: Aplica el commit especificado en la rama actual.
  
         git cherry-pick abc123
 
- *git cherry-pick --no-commit <commit>*: Aplica los cambios del commit especificado pero no realiza automáticamente el commit. Esto permite realizar modificaciones adicionales antes de realizar el commit.

        git cherry-pick --no-commit abc123


- *git cherry-pick -n <commit>*: Equivalente a git cherry-pick --no-commit.

        git cherry-pick -n abc123
 
- *git cherry-pick --edit <commit>*: Abre el mensaje de commit en un editor de texto antes de realizar el commit, permitiéndote modificar el mensaje del commit.

        git cherry-pick --edit abc123

<br>

**git bisect:** Sirve para buscar errores en todos los commits del proyecto.

1. Comenzamos utilizando el comando *git bisect start*:
     - Este comando te llevaría al primer commit de tu proyecto.

<br>

2. Una vez allí tendremos que ir indicando si los commits son correctos o tienen algun fallo con los siguientes comandos:
     - Para eso estan *git bisect good* y *git bisect bad*.
<br>

3. Cuando encuentres el fallo usando *git bisect reset*, para volver a la version más reciente de tu codigo.
   
# Bibliografía

https://aprendeconalf.es/docencia/git/manual/manual-git.pdf

https://unity.com/es/solutions/what-is-version-control

https://ed.team/blog/que-es-git-y-como-funciona

https://www.freecodecamp.org/espanol/news/aprende-los-conceptos-basicos-de-git-en-menos-de-10-minutos/

https://www.atlassian.com/es/git/tutorials/inspecting-a-repository/git-tag#:~:text=Las%20etiquetas%20son%20referencias%20que,una%20rama%20que%20no%20cambia.

https://www.atlassian.com/es/git/tutorials/why-git#:~:text=Una%20de%20las%20mayores%20ventajas,entre%20muchos%20usuarios%20de%20Git.

https://www.siteground.es/kb/estructura-git-contenido-repositorio/

https://www.hostinger.es/tutoriales/mejores-clientes-git-gui#1_QGit

https://www.hostinger.es/tutoriales/comandos-de-git

https://kinsta.com/es/blog/git-avanzado/

https://desarrollowp.com/blog/tutoriales/aprende-git-de-manera-sencilla-comandos-avanzados/


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

### Clientes Git para Windows
1. Sourcetree: Se puede usar también para Mac. Se admiten archivos Git grandes y permite visualizarlos con diagramas de ramificación detallados. Tiene una búsqueda de confirmación local que permite encontrar cambios de archivo, confirmaciones y ramas. 
2. Github: Se define básicamente como una extensión del flujo de trabajo en Github. Permite administrar el código sin necesidad de escribir comandos.

### Clientes Git para Mac
1. GitUp: Viene con un kit de herramientas que perite crear aplicaciones de Git. Tiene una función de Mapa en vivo que permite ver el progreso del proyecto sin actualizarlo. 
2. GitBox: Con este cliente se pued