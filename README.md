# **CURSO GIT**
# CONCEPTOS
## **Clase 1**
**Git:**
Sistema de control de versiones distribuido, cada desarrollador trabaja en una rama diferente. Posteriormente, estas ramas se fusionan de nuevo en la rama principal.

**repositorio:**
Almacen de versiones de los ficheros de un proyecto y sus históricos.

**Control de versiones:** 
Sistema que registra cada cambio que hacemos, permite tener un historico de los cambios, cuando se hicieron y quien los hizo. Importante por rendimiento y es flexible.

**CVS:**
(Concurrent Version System}, es el primer control de versiones.

**Estados de git:**
1. **Modified:** Archivos con cambios no confirmados.
2. **Staged:** Archivo marcado como preparado para ser confirmado.
3. **Commited:** Archivo grabado en el repositorio local (commit).

**Commit:** 
Registrar cambios del repositorio. Como una fotografía con autor, fecha y localización.

**Head:** 
Puntero que referencia el punto actual en el historial de cambios.
****
## **Clase 2**
**Rama de git:**
Es un snapshot, para bifurcaciones y desarrollo no lineal, colaborativo e independiente.

**Conflictos a fusionar 2 Ramas:**
Se da cuando Git no puede determinar que cambio es mas importante que otro.
****
## **Clase 3**

# COMANDOS
## **Clase 1**
**COMANDO: git init**

Comando para inicializar Git en un directorio.

Primera forma:
1. git init `<nombre Proyecto>`
2. cd `<Proyecto>`

Segunda forma:
1. cd `<directorio de Proyecto>`
2. git init

**COMANDO: git add `<file>`**

Indica a Git que quieres incluir actualizaciones en un archivo/directorio. Pasa de Modified a Staged.

**COMANDO: git status**

Descripción del árbol de trabajo y ver el estado de los archivos.

**COMANDO: git restore**
1. git restore `<file>`
2. git restore --staged `<file>`

 `1` restaura un archivo al estado del último commit. `2` quitar un archivo del área de staged y restaurarlo al estado del último commit.

**COMANDO: git commit**

Confirmar los cambios realizados en el repositorio.
1. git commit `<file>`
2. git commit -m `<descripción>`
3. git commit -m `<Título>` -m `<descripción>`
4. git commit --ammend -m `<descripción>`

`4` sobreescribir la descripcion del ultimo commit, cambiando el ID y ocultando el commit que se queria cambiar.

**COMANDO: git log**

Ver el historial de commits en el repositorio Git.
1. git log
2. git log --oneline
3. git log --graph
4. git --graph --oneline

`2` solo ver descripcion de commits. `2` de forma grafica.
****
## **Clase 2**
**COMANDO: git branch**
1. git branch
2. git branch -d `<nombre Rama>`
3. git branch -D `<nombre Rama>`
4. git branch `<nombre de nueva rama>`

`1` ver ramas disponibles. `2` eliminar una rama. `3` eliminar una rama forzadamente. `4` crear nueva rama.

**COMANDO: git switch**

Ingresar o cambiar a una rama.
1. git switch `<nombre Rama>`
2. git switch -c `<nombre Rama>`

`1` Solo ingresar. `2` crear e ingresar a la nueva rama.

**COMANDO: git merge**

Fucionar Ramas
1. git merge --edit
2. git merge --abort
3. git merge --no-commit
4. git merge `<nombre Rama>`
5. git merge `<nombre Rama>` --no--ff

`1` abre el editor antes de hacer commit. `2` cancelar una operación de fusión que se encuentra en curso. `3` evita el commit automatico. `4` trae los cambios de esa rama a la rama actual. `5` Git creará un commit de fusión adicional.
****
## **Clase 3**
