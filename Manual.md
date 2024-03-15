
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