## CREACIÓN Y ACTUALIZACIÓN DE REPOSITORIOS

EJERCICIO 1

Los comandos utilizados son los siguinentes:
	git config --global user.name "Adrián Martín"
	git config --global user.email "adrian.martin@gruposantander.com"


EJERCICIO 2

Para crear un repositorio libro:
1. Se crea la carpeta cuyo nombre sea "libro" -> mkdir libro
2. Entramos en la carpeta recién creada -> cd libro
3. Iniciamos el repositorio de esta carpeta -> git init 

En este instante el repositorio se encuentra vacío. 


EJERCICIO 3

1. Para comprobar el estado del repositorio se utilizará "git status".
2. La creación del fichero "indice.txt" se hará utilizando el siguiente comando -> echo . > indice.txt
2.1. Se entra de manera manual en el fichero recién creado, cuyo contenido de momento será de "." y actualizamos el contenido al requerido en el proyecto. 
3. Se hará de nuevo "git status" para comprobar el contenido del repositorio. (Aparece el fichero "indice.txt" sin 'trackear')
4. Con "git add ." añadiré el fichero a la zona de intercambio temporal.
5. Se hará de nuevo "git status" para comprobar el contenido del repositorio. (Aparece el fichero "indice.txt" 'trackeado')


EJERCICIO 4

1. Para realizar el commit -> git commit -m "Añadido índice del libro"
2. Con "git status" se apreciará el estado del repositorio. (Aparece 'On branch master
nothing to commit, working tree clean')


EJERCICIO 5

1. Manualmente modificamos el archivo
2. Para mostrar los cambios se utilizará el comando "git diff". (Mostrará la modificación del 'Capítulo 3' y el nuevo Capítulo 4'). 
3. "git add . " para llevar el archivo a la zona de intercambio temporal y "git commit -m "Añadido capítulo 3 sobre gestión de ramas" ".


EJERCICIO 6

1. Para mostrar la última versión utilizaremos "git diff"
2. Con "git commit --amend" cambiamos el último mensaje. Luego 'ESC' y ':wq'. 
3. Con "git log" se mostrarán los últimos cambios del repositorio. 


## MANEJO DEL HISTORIAL DE CAMBIOS

EJERCICIO 1

1. Para mostrar el historial de cambios del repositorio se utilizará "git log". 
2. Se crea la carpeta cuyo nombre sea capitulos-> mkdir capitulos
2.1. Entramos en la carpeta recién creada -> cd capitulos
3. Hacemos git add . 
4. Se hace el commit -> "echo Git es un sistema de control de versiones ideado por Linus Torvalds > capitulo1.txt"
5. Para mostrar el historial -> git log


EJERCICIO 2

1. Crear fichero -> echo . > capitulo2.txt
1.1. Manualmente escribimos todo el contenido del caítulo 2. 
2. Lo añadimos a la zona temporal "git add . " 
3. git commit -m " Añadido capítulo 2"
4. Utilizaremos el comando "git log -p -2". 


EJERCICIO 3

1. Crear fichero -> echo . > capitulo3.txt
1.1. Manualmente escribimos todo el contenido del caítulo 3. 
2. Lo añadimos a la zona temporal "git add . " 
3. git commit -m " Añadido capítulo 3"
4. Utilizaremos el comando "git log" para buscar los hash
4.1. Compararemos los hash del primer y último commit -> git diff "'hash1'..'HEAD'"


EJERCICIO 4

1. Mediante el comando "echo Capítulo 5: Conceptos avanzados >> indice.txt" añadiremos a la última fila del fichero "indice.txt" el texto sugerido. 
2. "git add ."
3. Con el comando "git commit -m "Añadido capítulo 5 al índice" " se realizará el commit. 
4. Con el comando "git blame indice.txt" se verá quién ha hecho cambios sobre el fichero "indice.txt". 


## DESHACER CAMBIOS

EJERCICIO 1

1. Se elimina manualmente la última línea del fichero.
2. Con "git status" comprobamos el estado del repositorio. (Mostrará modificado)
3. Para deshacer los cambios se utilizará "git checkout -- indice.txt"
4. Con "git status" se comprobará el estado del repositorio


EJERCICIO 2

1. Se borra manualmente
2. Con "git add ." añadimos los archivos a la zona temporal
3. Con "git status" vemos el estado del repositorio
4. Con "git reset indice.txt"
5. "git status"
6. Se utilizará "git checkout -- indice.txt"
7. "git status"


EJERCICIO 3

1. Se borra manual
2. Se borra manual
3. echo > capitulo4.txt
4. git add .
5. git status
6. git reset
7. git status
8. "git checkout -- . "
9. git status


EJERCICIO 4

1. Se borra manual y "git add  ."
2. Se borra manual
3. "git add ." y "git commit -m "Borrado accidental" "
4. "git status"
5. "git reset HEAD~1"
6. "git log" y "git status"
7. git commit -m "Borrado accidental"
8. "git checkout -- ."
9. "git log" y "git status"


## GESTIÓN DE RAMAS

EJERCICIO 1

git branch bibliografia
 

EJERCICIO 2

1. "echo > capitulo4.txt"
1.1. Manualmente relleno el contenido del capitulo4
2. git add . 
3. git commit -m "Añadido capítulo 4"
4. git log --graph --all --decorate --oneline


EJERCICIO 3

1. "git checkout bibliografia"
2. "echo > bibliografia.txt"
3. git add .
4. git commit -m "Añadida primera referencia bibliográfica"
5. "git log --graph --all --decorate --oneline"


EJERCICIO 4

1. "git checkout master" y "git merge bibliografia"
2. "git log --graph --all --decorate --oneline"
3. "git branch -d bibliografia"
4. "git log --graph --all --decorate --oneline"


EJERCICIO 5

1. "git branch bibliografia"
2. "git checkout bibliografia"
3. Se hará manual
4. "git add ." y "git commit -m "Añadida nueva referencia bibliográfica"
5. "git checkout master"
6. Manual
7. "git add ." y "git commit -m "Añadida nueva referencia bibliográfica"
8. "git checkout master" y "git merge bibliografia"
9. Manual
10. "git add ." y "git commit -m "Resuelto conflicto bibliografía"
11. "git log --graph --all --decorate --oneline"


## REPOSITORIOS REMOTOS

EJERCICIO 1

1. De manera manual
2. "git remote add libro https://github.com/adrianmartinmartin/libro-git.git"
3. git remote -v


EJERCICIO 2

1. git push -u libro master
2. Los cambios se reflejan en el repositorio remoto. "git log --graph --all --decorate --oneline"


EJERCICIO 3

1. Colaboro con Álvaro
2. "git clone https://github.com/alvarogarciapiz/libro-git.git"
3. "echo "adrianmartinmartin adrian.martin@gruposantander.com" > autores.txt "
4. " git add ."
5. "git commit -m "Añadido autor" "
6. git push 


EJERCICIO 4

1. fork en github
2. "git clone https://github.com/adrianmartinmartin/libro-git-1.git"
3. git checkout -b auditoria
4. Manual
5. git add .
6. git commit -m "Añadido nuevo autor"
7. "git push origin auditoria"
8. Pull Request hecho en Github
