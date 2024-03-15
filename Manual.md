
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


