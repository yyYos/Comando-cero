Existen areas que nombra git para difenciar en que estado se encuentra los archivos agregados, eleminados o modificados, esto para que sea mejor la administración de las versiones de estos.

_Area del Disco Duro_
Esta area la llama Untracked (sin seguimiento), estos son archivos que no estan agregados a git(git add nombre.txt) y por ende git no sabe de la existencia de este.

_Area entre Disco Duro y Git_
Esta se llama Unstaged a esta pertenecen los archivos que ya estan en git( git repository ) pero son archivos que no estan actualizados.

_Area de Espera (staging)_
Se guarada temporalmente en la memoria RAM
Los archivos en esta area fueron modificados por el comando git add, este los agrega a esta area, esta dice que aun no esta en repositorio pero que esta en espera de agregarse estos archivos. Tambien en este momento se puede decir que son archivos tracked, ya que si son rastreables.

_Area de Repositorio_
Esta se llama Tracked, son archivos que se pueden rastrear ya que se encuentra dentro de git repository, el cual es una carpeta(/.git/) donde se encuentran todos los archivos modificacos con git commit.


## Configuracion para GIT
Debes ingresar el email y nombre de usuario de la persona que estara haciendo los modificaciones o agregando nuevos archivos al repositorio

git config --global user.email
git config --global user.name

Esto permite saber cuales son los datos basicos de la persona que esta generando cambios al repositorio.