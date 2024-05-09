# **CURSO GIT**
# CONCEPTOS
## **Clase 1**
**Git:**
Sistema de control de versiones distribuido, donde cada desarrollador trabaja en una rama diferente. Posteriormente, estas ramas se fusionan de nuevo en la rama principal.

**repositorio:**
Pude ser visto como un almacen de versiones de los ficheros de un proyecto y sus históricos.

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
****
## **Clase 2**
