# Manipulación Básica de Git

Realizado por: __Cleyber Esteban Garcia Marval__  
Nº Lista: __7__  
Curso: __1º DAM__

**Índice**
1. [Configuración](#id1)
2. [Creación de un repositorio](#id2)
3. [Comprobando el estado del repositorio](#id3)
4. [Realizando commit's](#id4)
5. [Modificación de ficheros](#id5)
6. [Historia](#id6)


## Tarea: Configuración <a name="id1"></a>

#### Operaciones a realizar:
```code
git config --global user.name "Your-Full-Name"
git config --global user.email "your-email-address"
git config --global color.ui auto
git config --list 
``` 

#### Salida:
```code
user.email=designercgm@gmail.com
user.name=Cleyber Esteban Garcia Marval
color.ui=auto
```


 ## Tarea: Creación de un repositorio <a name="id2"></a>
 #### Crear un repositorio nuevo con el nombre dpl y mostrar su contenido
 #### Operaciones a realizar: 
 ```code
 mkdir dpl
 cd dpl
 git init
 ls -la
 ```
#### entrada:
- mkdir dpl
- cd dpl
- git init

#### salida:
```code
ayuda: Usando 'master' como el nombre de la rama inicial. Este nombre de rama predeterminado
ayuda: está sujeto a cambios. Para configurar el nombre de la rama inicial para usar en todos
ayuda: de sus nuevos repositorios, reprimiendo esta advertencia, llama a:
ayuda: 
ayuda: 	git config --global init.defaultBranch <nombre>
ayuda: 
ayuda: Los nombres comúnmente elegidos en lugar de 'master' son 'main', 'trunk' y
ayuda: 'development'. Se puede cambiar el nombre de la rama recién creada mediante este comando:
ayuda: 
ayuda: 	git branch -m <nombre>
Inicializado repositorio Git vacío en /home/esteban/dpl/.git/

```
#### entrada:
- ls -la
#### salida:
```code
total 12
drwxrwxr-x  3 esteban esteban 4096 oct  4 14:59 .
drwxr-x--- 27 esteban esteban 4096 oct  4 14:59 ..
drwxrwxr-x  7 esteban esteban 4096 oct  4 14:59 .git
```

## tarea: Comprobando el estado del repositorio <a name="id3"></a>
 
 - Comprobar el estado del repositorio.
 - Crear un fichero indice.txt con el siguiente contenido:
   - Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)
   - Capítulo 2: Flujo de trabajo básico
 - Comprobar de nuevo el estado del repositorio.
 - Añadir el fichero a la zona de intercambio temporal.
 - Volver a comprobar una vez más el estado del repositorio

#### Operaciones a realizar:
```code
 git status
 cat > indice.txt
 Capítulo 1: Instalación de Git por el alumno XXX
 Capítulo 2: Flujo de trabajo básico
 Ctrl+D
 git status
 git add indice.txt
 git status
```
#### entrada:
 - git status

#### salida:
```code
En la rama master

No hay commits todavía

no hay nada para confirmar (crea/copia archivos y usa "git add" para hacerles seguimiento)
```
#### entrada:
 - cat > indice.txt
 - Capítulo 1: Instalación de Git por el alumno XXX
 - Capítulo 2: Flujo de trabajo básico
 - Ctrl+D
 - git status

#### salida:
```code
En la rama master

No hay commits todavía

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
	indice.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
```
#### entrada:
- git add indice.txt
- git status

#### salida:
```code
En la rama master

No hay commits todavía

Cambios a ser confirmados:
  (usa "git rm --cached <archivo>..." para sacar del área de stage)
	nuevos archivos: indice.txt
```



## Tarea: Realizando Commit's <a name="id4"></a>
#### Realizar un commit de los últimos cambios con el mensaje __Añadido índice de la asignatura DPL.__ y ver el estado del repositorio.

#### Operaciones a realizar:
```code
git commit -m "Añadido índice de la asignatura DPL."
git status
```
#### entrada:
- git commit -m "Añadido índice de la asignatura DPL

#### salida:
```code
[master (commit-raíz) 558e2fd] Añadido indice de la asignatura DPL
 1 file changed, 2 insertions(+)
 create mode 100644 indice.txt
```

#### entrada:
- git status

#### salida:
```Code
En la rama master
nada para hacer commit, el árbol de trabajo está limpio
```

## Tarea: Modificación de ficheros <a name="id5"></a>
 - Cambiar el fichero indice.txt para que contenga lo siguiente:
   - Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)
   - Capítulo 2: Flujo de trabajo básico
   - Capítulo 3: Gestión de ramas
   - Capítulo 4: Repositorios remotos
- Mostrar los cambios con respecto a la última versión guardada en el repositorio.
- Hacer un commit de los cambios con el mensaje __Añadido los capitulos 3 y 4.__

#### Operaciones a realizar:
```code
cat > indice.txt
Capítulo 1: Instalación de Git por el alumno XXX _(donde XXX es el nombre del alumno)_
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Gestión de ramas
Capítulo 4: Repositorios remotos
Ctrl+D
git diff
git add indice.txt
git commit -m "Añadido los capitulos 3"
```

#### entrada:
- cat > indice.txt
- Capítulo 1: Instalación de Git por el alumno XXX _(donde XXX es el nombre del alumno)_
- Capítulo 2: Flujo de trabajo básico
- Capítulo 3: Gestión de ramas
- Capítulo 4: Repositorios remotos
- Ctrl+D
- git diff

#### salida:
```code
diff --git a/indice.txt b/indice.txt
index d4e5bff..0f817c5 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,2 +1,4 @@
-Capítulo 1: Instalación de Git por el alumno XXX
+Capítulo 1: Instalación de Git por el alumno Cleyber Esteban Garcia Marval
 Capítulo 2: Flujo de trabajo básico
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
```

#### entrada:
- git add indice.txt
- git commit -m "Añadido los capitulos 3 y 4"

#### salida:
```code
[master 34edc5a] Añadido los capitulos 3 y 4
 1 file changed, 4 insertions(+), 2 deletions(-)
```

## Tarea: Historia <a name="id6"></a>
- Mostrar los cambios de la última versión del repositorio con respecto a la anterior.
- Cambiar el mensaje del último commit por Añadido el capitulo sobre gestión de ramas al índice.
- Volver a mostrar los últimos cambios del repositorio.

#### Operaciones a realizar:
```code
git show
git commit --amend -m "Añadido el capitulo sobre gestión de ramas al indice."
git show
```

#### entrada:
- git show

#### salida:
```code
commit 34edc5a131ce7bbba67fb98acd667b68ed56eceb (HEAD -> master)
Author: Cleyber Esteban Garcia Marval <designercgm@gmail.com>
Date:   Wed Oct 4 15:35:48 2023 +0100

    Añadido los capitulos 3 y 4

diff --git a/indice.txt b/indice.txt
index 1e1ee14..0f817c5 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,2 +1,4 @@
-- Capítulo 1: Instalación de Git por el alumno Cleyber Esteban García Marval
-- Capítulo 2: Flujo de trabajo básico
\ No newline at end of file
+Capítulo 1: Instalación de Git por el alumno Cleyber Esteban Garcia Marval
+Capítulo 2: Flujo de trabajo básico
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
```

#### entrada:
- git commit --amend -m "Añadido el capitulo sobre gestión de ramas al indice"

#### salida:
```code
[master 3b5ec6a] Añadido el capitulo sobre gestión de ramas al indice.
 Date: Wed Oct 4 15:35:48 2023 +0100
 1 file changed, 4 insertions(+), 2 deletions(-)
```

#### entrada:
- git show

#### salida:
```code
Author: Cleyber Esteban Garcia Marval <designercgm@gmail.com>
Date:   Wed Oct 4 15:35:48 2023 +0100

    Añadido el capitulo sobre gestión de ramas al indice.

diff --git a/indice.txt b/indice.txt
index 1e1ee14..0f817c5 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,2 +1,4 @@
-- Capítulo 1: Instalación de Git por el alumno Cleyber Esteban García Marval
-- Capítulo 2: Flujo de trabajo básico
\ No newline at end of file
+Capítulo 1: Instalación de Git por el alumno Cleyber Esteban Garcia Marval
+Capítulo 2: Flujo de trabajo básico
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
```


