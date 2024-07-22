
# **CURSO GIT**
# CONFIGURAR GIT
**Git:**
Sistema de control de versiones distribuido, cada desarrollador trabaja en una rama diferente. Posteriormente, estas ramas se fusionan de nuevo en la rama principal.

Nombre de usuaio y correo electronico en Git que son el mismo que GitHub:
```bash
git config --global user.name "<Tu nombre>"
git config --global user.email "<Tu correo>"
```
 Comprobar configuracón de Git:
```bash
git config --list
git config -l
```
**repositorio:**
Almacen de versiones de los ficheros de un proyecto y sus históricos.

**Control de versiones:** 
Sistema que registra cada cambio que hacemos, permite tener un historico de los cambios, cuando se hicieron y quien los hizo. Importante por rendimiento y es flexible.

**CVS:**
(Concurrent Version System), es el primer control de versiones.
## configuraciones extras
configurar alias:
  ```bash
git config --global alias.stats "<comando git sin "git">"
git stats
```

# COMANDOS
## git add
Indica a Git que quieres incluir actualizaciones en un archivo/directorio. Pasa de Modified a Staged.
```bash
git add .
git add <file>
```
## git blame
Ma última modificación de cada línea en un archivo, mostrando información sobre el commit y el autor.
  ```bash
git blame <archivo>
```
Ver información mas detallada y legible:
  ```bash
git blame -c <archivo>
```
Especificar un rango de lineas (del 12 a 24):
  ```bash
git blame <archivo> -L12,24
git blame <archivo> -L12,24 -c
```
## git branch
Ver ramas disponibles:
```bash
git branch
git branch -a
```
Eliminar una rama local:
  ```bash
git branch -d <nombre Rama>
git branch -D <nombre Rama>
```  
Crear una nueva rama:
```bash
git branch <nombre de nueva rama>
```
Renombrar una rama en Git. La opción -M es un atajo para --move --force, lo que significa que Git forzará el renombramiento incluso si una rama con el nuevo nombre ya existe.
```bash
git branch -M <nombre de nueva rama>
```
**Rama de git:**
Es un snapshot, para bifurcaciones y desarrollo no lineal, colaborativo e independiente.

**Conflictos a fusionar 2 Ramas:**
Se da cuando Git no puede determinar que cambio es mas importante que otro.
## git checkout
Cambiar de rama o restaurar archivos en el árbol de trabajo.
Cambiar a una rama específica:
```bash
git checkout <nombre rama>
```
Restaurar un Archivo a un Commit Específico:
```bash
git checkout <commitID>
```
## git clone
Clonar un repositorio con todas sus ramas y archivos:
```bash 
git clone <URL repositorio GitHub>
```
## git commit
**Commit:** 
Registrar cambios del repositorio. Como una fotografía con autor, fecha y localización.

Confirmar los cambios realizados en el repositorio:
  ```bash
git commit
git commit -m "<descripción>"
git commit -m "<Título>" -m "<descripción>"
```
Para sobreescribir la descripcion del ultimo commit, cambiando el ID y ocultando el commit cambiado:
  ```bash
git commit --ammend -m "<descripción>"
```
Realizar dos acciones de manera combinada, agregar (stages) y confirmar (commits) los cambios realizados en el repositorio:
  ```bash
git commit -am "<descripción>"
```
## git diff
Ver cambios no preparados:
```bash 
git diff
```
Ver diferencias:
```bash 
git diff <commit1> <commit2>
git diff <rama1> <rama2>
```
## git grep
ver donde y cuantas veces se uso una palabra:
```bash 
git grep <palabra>
```
Ver en que linea se uso la palabra:
```bash 
git grep -n <palabra>
```
Cuantas veces aparece la palabra:
```bash 
git grep -c <palabra>
```
## git init
Comando para inicializar Git en un directorio. Existen 2 formas.
```bash
git init <nombre Proyecto>
cd <Proyecto>
```
```bash
cd <directorio de Proyecto>
git init
```
## git log
Ver el historial de commits en el repositorio Git.
  ```bash
git log
```
Ver todo el historial de commits en el repositorio Git.
  ```bash
git log --all
```
Ver solo descripcion de los commits:
  ```bash
git log --oneline
```
Ver los commits de forma grafica con conexiones:
  ```bash
git log --graph
```
```bash
git --graph --oneline
git log --all --graph
git log --all --graph --decorate
git log --all --graph --decorate --oneline
```
Buscar la palabra en los comentarios de los commit`s:
  ```bash
git log -S "<palabra>"
```
**Head:** 
Puntero que referencia el punto actual en el historial de cambios.
## git merge
Traer los cambios de una rama a la rama actual:
 ```bash 
git merge <nombre Rama>
```
Abrir el editor antes de hacer commit:
```bash 
git merge --edit
```
cancelar una operación de fusión que se encuentra en curso:
```bash 
git merge --abort
```
Evitar el commit automático:
 ```bash 
git merge --no-commit
```
Git creará un commit de fusión adicional:
 ```bash 
git merge <nombre Rama> --no--ff
```
## git push 
Una vez que los repositorios esten enlazados se sicronizan los cambios del repositorio local y remoto, puede usarse uno de los siguientes:
```bash 
git push --all
git push origin <nombre Rama>
```
Subir los cambios locales de una rama específica a un repositorio remoto, y al mismo tiempo, establece una relación de seguimiento entre la rama local y la rama remota:
```bash 
git push -u origin <nombre Rama>
```
## git pull
Descargar cambios del repositorio remoto(GitHub) al local.
```bash 
git pull
```
Actualizar la rama con los cambios más recientes del repositorio remoto origin
```bash 
git pull origin <nombre rama>
```
## git reflog
Muestra un registro de todos los cambios que se han hecho en el puntero HEAD.
```bash 
git reflog
```
## git remote
Enlazar un repositorio local con uno remoto, un repositorio local puede tener enlazados varios repsitorios remotos:
 ```bash 
git remote add origin <URL repositorio GitHub>
```
Eliminar ramas remotas de mi repositorio local que ya no se usan:
```bash 
git remote prune origin
```
Ver que repositorios remotos estan enlazados con el repositorio local:
```bash 
git remote -v
```
Eliminar un enlace:
```bash 
git remote remove origin
```
Cambia la URL del remoto origin a una nueva URL:
 ```bash 
git remote set-url origin <URL repositorio GitHub>
```
## git reset
Es una mala practica pero e usa como ultimo recurso.
Restablece HEAD: Mueve el puntero HEAD al commit especificado por <ID commit>.
 ```bash 
git reset  --hard <ID commit>
```
## git restore
Restaura un archivo al estado del último commit.
 ```bash
git restore <file>
```
Quitar un archivo del área de staged y restaurarlo al estado del último commit.
  ```bash
git restore --staged <file>
```
## git rm
Eliminar archivos del índice de Git y del árbol de trabajo.
```bash
git rm <file>
git rm <file1> <file1>
```
Para conservar el archivo y solo eliminar el ultimo add:
```bash
git rm --cached <file>
```
## git shortlog
Cuantos comits hizo cada miembro, incluyendo merges:
  ```bash
git shortlog -sn
```
Cuantos comits hizo cada miembro, incluyendo eliminados y merges:
  ```bash
git shortlog -sn --all
```
  ```bash
git shortlog -sn --all --no-merges
```
## git show
Ver detalles de un commit específico:
```bash
git show <SHA_del_commit>
```
Ver el commit más reciente:
```bash
git show
```
## git status
Descripción del árbol de trabajo y ver el estado de los archivos.
```bash
git status
```
**Estados de git:**
1. **Modified:** Archivos con cambios no confirmados.
2. **Staged:** Archivo marcado como preparado para ser confirmado.
3. **Commited:** Archivo grabado en el repositorio local (commit).
## git switch
Ingresar a una rama:
```bash 
git switch <nombre Rama>
```
Crear e ingresar a la nueva rama:'
```bash 
git switch -c <nombre Rama>
```


# LLAVE SSH
Recomendable hacerlo en el directorio home, no en algun proyecto.
Crear la llave:
```bash 
ssh-keygen -t rsa -b 4096 -C "<Tu correo>"
```
Ver el pid de la llave:
```bash 
eval $(ssh-agent -s)
```
Vamos al directorio donde se creo la llave ("cd /.ssh" en caso de ser home)
```bash 
ssh-add ~/.ssh/id_rsa
```
Conectar nuestro repositorio local a la ssh:
```bash 
git remote set-url origin <URL llave ssh GitHub>
```

# GIT EXTRA
## alias
Crear alias o atajos de comandos
```bash 
alias <nombre alias>="<comando git>"
```
Eliminar una alias:
```bash 
unalias <nombre alias>
```
## Tags
Agregar un tag, el nombre puede ser(v1.0), el PID puede ser de solo 6 dígitos:
```bash 
git tag -a <nombre tag> -m "<descripcion>" <PID commit>
```
Ver tags:
```bash 
git tag
```
```bash 
git show-ref --tags
```
Mandar tags a repositorio remoto:
```bash 
git push origin --tags
```
Eliminar tag:
```bash 
git tag -d <nombre tag>
git push origin --tags
git push origin :refs/tags/<nombret tag>
```
## Manejar ramas
Ver ramas con sus cambios
```bash 
git show-branch
git show-branch --all
```
ver todos los cambios del repositorio con una interfaz gráfica:
```bash 
gitk
```

# GITHUB
## ISSUES
## PULL REQUEST
## ACTIONS
## PROJECTS
## WIKI
## SECURITY