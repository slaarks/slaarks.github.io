---
title: GIT - Dejar de tracker archivos que ya fueron agregados al repositorio .git
published: true
---

A veces pasa que hacemos nuestro primer commit sin haber agregado un archivo `.gitignore` a nuestro proyecto, y comenzamos a tracker archivos que realmente no nos interesan como logs, clases compiladas, o archivos generados por nuestro IDE o nuestra herramienta de construcción.

En el mejor de los casos, el fastidio se reduce a ver como git muestra como modificado el repositorio por el simple hecho de levantar el proyecto y generar archivos .log, en el peor de los casos, puede que ya ni levante debido a algún conflicto de configuraciones locales (de gradle por ejemplo).

La solución es limpiar el repositorio .git, el problema es que a estas alturas, (aunque necesario) ya no es suficiente agregar el archivo `.gitignore`, proque los archivos ya fueron indexados, de modo que luego de agregar el archivo `.gitignore`, hay que sacar los archivos del repositorio .git y luego volver a meterlos, como esta vez ya habrá un archivo `.gitignore` actuando como filtro, solo volverán a entrar aquellos archivos que de hecho, necesitamos. El procedimiento es el siguiente:

* Agrega un archivo .gitignore (puedes ocupar [gitignore.io](http://gitignore.io/) para crear uno que se adapte a tus necesidades).

* Saca todos los archivos del repositorio .git:
```bash
git rm -r --cached .
```

Opcionalmente puedes optar por sacar solo un archivo:
```bash
git rm --cached <file>
```

O solo una carpeta:
```bash
git rm -r --cached <folder>
```

* Vuelve a agregar los archivos al repositorio .git, esta vez solo entrarán los que superen el filtro del archivo `.gitignore`:
```bash
git add .
git commit -am "Remove ignored files"
```

Opcionalmente, puedes hacerlo todo en un solo paso:
```bash
git rm -r --cached . && git add . && git commit -am "Remove ignored files"
```

Nota que esto solo elimina los archivos de tu repositorio .git, pero puede que aún haya archivos basura en tu workspace estropeando algo. Sé que de seguro existe una solución más elegante, pero si quieres dejar tu workspace completamente limpio, puedes hacer un push al repositorio remoto luego de las operaciones anteriores, y después volver a clonarlo: como solo se irán los archivos que admite el `.gitignore`, el clon que recuperes, será una versión prístina de tu proyecto.

Espero que este truco te sea de utilidad. ¡Hasta la próxima!

