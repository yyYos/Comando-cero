_Iniciar git, crea una carpeta (/.git/) donde guarda todos los archivos modificados con git commit_
git init

_Agregar achivos al area staged
git add nombreArchivo.txt
git add . <-- (Agrega todos los archivos)

_Agregar archivos al area de repositorio (carpeta /.git/)_
git commit -m "mensaje"
o
git commit -am "mensaje"

_Remover archivos de git, solo pertecen a nuestro disco duro
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
