## Crear una rama

Para crear una rama, la rama principal siempre sera la rama master, se puede cambiar el nombre pero no es la mejor practica
git branche nombreRama

Para entrar a esa rama
git checkout nombreRama

_Automaticamente el HEAD(indicador) se pasa a esta nueva rama y ya no esta en master_

Al cambiar de rama pero no hemos echo commit, madara un error la consola, hasta no estar en el repositorio y si podremos perder los cabios

_Cambiarnos de rama_
git checkout nombreRama

## Unir dos ramas

Para esto nos posicionamos en la rama a donde queremos unir la rama en muchos casos en la rama master, en caso que no haya conflictos no mostrara ningun error.

Para unir dos ramas, se le dice merge pero en realidad es un commit el cual tambien tiene un mensaje
git merge nombreRama

En caso que haya un CONFLICTO mostrara un mensaje y muestra el nombre del archivo en conflicto, muestra en el archivo los dos cambios en el momento, esto sirve para saber que es lo que esta en master y que es lo que tiene la otra rama.
La separacion de este son con caracteres como <<<<<< HEAD, ------ y >>>>>> nombreRama, la solucion mas correcta es borrar el codigo que no se quiere checar cada conflicto y volver hacer el merge, que en la teoria es un commit

_Borrar branch_
git branch -D nombreRama
_Saber de las ramas remotas_
git branch -r
git branch -a