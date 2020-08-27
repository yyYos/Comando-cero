Para que nosotros podamos guardar nuestro proyecto en un repositorio web, ocupaemos el mas conocito GitHub, este tiene en sus servidores un git instalado, el cual podemos subir nuestros proyectos y compartilos con otras personas, es una herramineta colaborativa.

Creamos un repositorio, agregamos un nombre a ese repo y agregamos un readme, que es un archivo .md que se muestra al entrar a este repo en github, sirve para decirle a las personas de que se trata este repo, te pide una licencia seleccionamos none. Este crea una ruta, la cual tiene el repo nuevo.

Para copiar los archivos en esta ruta, copiamos la ruta https que nos y la agregamos a el siguiente comando, esto se hace desde la carpeta principal del proyecto que queremos.

Con este se crea un nombre, una referencia llamada origin, podemos cambiar el nombre
git remote add origin RUTAHTTP

_Muestra los repos que tenemos_
git remote -v

_Traer cambios que puden haber en el repo_
git pull origin master

_Subir todo los archivos modificados del proyecto a github_
git push origin master