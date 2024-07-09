
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

# COMANDOS
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
## git add
Indica a Git que quieres incluir actualizaciones en un archivo/directorio. Pasa de Modified a Staged.
```bash
git add .
git add <file>
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
## git restore
Restaura un archivo al estado del último commit.
 ```bash
git restore <file>
```
Quitar un archivo del área de staged y restaurarlo al estado del último commit.
  ```bash
git restore --staged <file>
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
## git log
Ver el historial de commits en el repositorio Git.
  ```bash
git log
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
```
**Head:** 
Puntero que referencia el punto actual en el historial de cambios.
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
## git switch
Ingresar a una rama:
```bash 
git switch <nombre Rama>
```
Crear e ingresar a la nueva rama:'
```bash 
git switch -c <nombre Rama>
```
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
## git clone
Clonar un repositorio con todas sus ramas y archivos:
```bash 
git clone <URL repositorio GitHub>
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