Para que nosotros podamos guardar nuestro proyecto en un repositorio web, ocupaemos el mas conocito GitHub, este tiene en sus servidores un git instalado, el cual podemos subir nuestros proyectos y compartilos con otras personas, es una herramineta colaborativa.

Creamos un repositorio, agregamos un nombre a ese repo y agregamos un readme, que es un archivo .md que se muestra al entrar a este repo en github, sirve para decirle a las personas de que se trata este repo, te pide una licencia seleccionamos none. Este crea una ruta, la cual tiene el repo nuevo.

Para copiar los archivos en esta ruta, copiamos la ruta https que nos y la agregamos a el siguiente comando, esto se hace desde la carpeta principal del proyecto que queremos.

_Con este traemos el repo a nuestro disco local con una referencia llamada origin, podemos cambiar el nombre_
git remote add origin RUTAHTTP

_Muestra los repos que tenemos_
git remote -v

_Traer cambios que puden haber en el repo_
git pull origin master

_Subir todo los archivos modificados del proyecto a github_
git push origin master

_Tags_
------
Nos permite indicar a git cuales son los commit mas importantes de nuestro proyecto, por ejemplo cambio de variables globales para tu proyecto.
Por lo general se nombran como v0.1,v0.2..., esto ya es a tu conciderancion.

_Saber que tags hay_
git tag
git show-ref --tags

_Agregar un tag y asignarlo a un commit_
git tag -a nombreTag commit

_Borrar tag localmente_
git tag -d nombreTag

_Publicar tag en repo remoto_
git push origin --tags

_Borrar tag del repo remoto_
git push origin _refs/tags/nombreTag

_Subir ramas a github_
----------------------
subir las ramas en la pagina de github que tengo en mi local
git push origin nombreRama

_pull request_
--------------
Es una momento antes de hacer el merge ya sea a la rama master o la rama de pruebas, este momento, este paso sirve para que los lideres de desarrollo aprueben los cambios y ahora si mamdarlos a master o a pruebas. Tecnicamente este trabajo lo hacen los devOps los cuales administran todo el desarrollo de integración.
Esto es propio de gitHub, estos pasos se hacen desde la pag. web de gitHub, y siendo colaboradora del proyecto
GitHub muestra una notificacion donde se agrega un comentario y lo que se a modificado, la persona encargada verificara cada modificacion del proyecto y aceptara el merge, esto tambien desde la pag.

_Creando un fork_
Si queremos colaborar con un proyecto sin ser colaboradores debemos crear un fork, esto pasa demasiado con los proyecto open source.Para colaboradores externos, personas que no estan dentro del proyecto pero quieren aportar a este, es una copia actual de repositorio.
Si lo que queremos es estar actalizados del proyecto que estamos aportando tendremo que agregar el repo a nuestro disco local.

_Saber de las ramas remotas_
git branch -r
git branch -a