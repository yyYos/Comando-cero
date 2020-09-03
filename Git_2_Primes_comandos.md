_Iniciar git, crea una carpeta (/.git/) donde guarda todos los archivos modificados con git commit_
git init
================================

_Agregar achivos al area staged
git add nombreArchivo.txt
git add . <-- (Agrega todos los archivos)

_Agregar archivos al area de repositorio (carpeta /.git/)_
git commit -m "mensaje"
o
git commit -am "mensaje"

_Remover archivos de git, solo pertenecen a nuestro disco duro
git rm  --cached

_Elimina archivos de git y del disco duro, puedes recuperarlos pero son comandos mas avanzados_
git rm --force

_Ramas para trabajar en equipo_
Crear copias de un repositorio en especifico para poder trabajar en cambios sin generar algun error de codigo, esto ayuda a la seguridad de no subir cambios que generen algun tipo de bug en el proyecto

git branch nombreRama

_Ver los cambios_
git show nombreArchivo.txt

_Ver los commit que hemos echo_
muestra el nombre de commit, la hora de commit y el mensaje del commit
git log --all --graph --decorate --oneline
git log --stat

_Ver todo el registro de git_
git reflog

_Ver las diferencias entre dos versiones del mismo archivo_
git diff nombreDeCommitQueDaGitV1 nombreDeCommitQueDaGitVActual

##Volver en el tiempo

(HEAD es el "indicador" que git le da a sus archivos en las areas staging y repositorio)
git reset HEAD 

NOTA: git reset elimina el historial de git(git log), lo que quiere decir que no podras regresar a futuros commits ya que se borraron.

git reset HEAD --soft (Borramos el historial y registro de Git pero guardamos los ultimos cambios en staging)
git reset HEAD --hard (Se borra completamente el historial y regitro de Git)

Tambien se puede regresar un archivo especifico de un HEAD(indicador) con cheakout

git chekout HEAD(indicador) nombreArchivo.txt

esto para git lo muestra en la area staging para solo hacer commit, este sin en cambio si nos dejara volver al futuro ya que no elimina el historial de git(git log)

_Para eliminar archivos de git_
Este no elimina el historial de sistemas de versiones.

git rm --cached elimina el archivo de la area staging pero los mantiene en el disco duro
git rm --force elimina archivos de GIT y del Disco Duro, pero se pueden recuperar con comando avanzados

_git rebase_
git rebase rama
Aunque es una mala practica se tiene este comando para integrar una rama al historial de la rama principal (por lo general master) sin indicar que se integraron cambios de una 2da rama y aun mas importante sin hacer merge de estas dos. Por ejemplo curioso, si hay un error y por azares del destino se te olvido integrarlo a tu rama master entonces puedes hacer un git rebase master desde tu 2da rama, esto trae todos los cambios de master y ahora desde la rama master git rebase 2daRama esto trae los cambios de la 2da rama sin hacer merge y dejar rastro de este cambio, vemos que con git log muestra los cambios de 2da rama pero sin especificar que viene de 2da rama, para git nunca existio esa rama, lo que quedaria es borrar la rama git branch -D 2daRama.
NOTA: git rebase a la rama donde se hacen las modificaciones despues git rebase a la rama final (master por ejemplo). Esto de manera local.

_git stash_
Crea un apartado temporal de el codigo que aun no tienes la certeza de hacer un commit, y supongamos que quieras cambiarte de rama pero por razones de que tienes modificaciones pendientes va crear un error y solo te dejara hasta que tengas esos cambios en tu repo local.
Para crear una rama desde un apartado temporal necesitas
git stash branch nombreRama
Para borrar un stash
git stash drop

_git clean_
Este comando borra archivo nuevos no es necesario que se trate de copia, no mostrara archivos modificados.
git clean --dry--run
Este para saber, simula que es lo que git va a borrar(ejecucion en seco)
git clean -f
Git borra los archivos que puede indexar, esto si no estan establecidos en .gitignore
git clean -df
Git borra las carpetas que simulaste en --dry--run

_git cherry-pick indicadorDeCommit_
indicadorDeCommit (esos numero raros que aparecen con git log)
Traer un commit especifico de otra rama, pero la rama aun no esta lista para un merge, con este comando decimos a git, solo quiero ese commit, no me interesan los demas commit si es que los hay.
Tienes que estar pocisionado en la rama donde quieres ese commit.
NOTA al combiar las ramas (merge) va ver conflictos, por el echo de que las dos ramas modificaron las mismas lineas por eso el error.

_git commit --amend_
Git puede agregar una modificacion al ultimo commit, que quiere decir, ejemplo si por error hicimos un commit pero me falto modificar algo se puede remendar el error con:

git commit --amend 

Esto tambien te da la oportunidad de modificar en mensaje del commit

_git reset_
Vuelve al commit que le ingresemos, puede ser que haga un reset manteniendo mis cambios o eliminar todas mis modificaciones por completo
git reset --soft indicadorDeCommit
git reset --hard indicadorDeCommit

Este puede servir en una situacion donde se cometio un grave error y deseas regresar a un commit 
donde estaba todo de maravilla.

_git grep_
Si queremos saber donde se encuentra alguna palabra, codigo, linea donde se encuentra la palabra en los documentos del proyecto
git grep -c palabra
git grep -n palabra

git log -s "palabra" essta es especial para saber cuantas veces escribi "palabra" en los commit

_Saber los commits de los integrantes_
git shortlog
git shortlog -sn
git shortlog -sn --all
git shortlog -sn --all --no-merges

_saber linea por linea quien modifico_
git blame -c nombreArchivo.txt
_Saber quien modifico el archivo especifico de las lineas especificas_
git blame rutaArchico -L12,20

_Saber que hace un comando_
git comando --help
