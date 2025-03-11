# 1. Inicializando el repositorio para nuestra cafetería ☕️

Vamos a crear un repositorio para gestionar las recetas de café de nuestra cafetería.

### Paso 1: Crear el repositorio

Para empezar, creamos un nuevo repositorio en GitHub llamado 'CafeteriaGitHub'.

1. Abre tu terminal.
2. Navega a la carpeta donde quieres crear el proyecto de tu cafetería.
3. Inicia un nuevo repositorio:

   ```bash
   git init

### Paso 2: Crear tu primer archivo
Crea un archivo llamado menu.txt con algunas recetas de café iniciales (no cometas el error que cometemos todos al empezar, ¡empieza solo con unas pocas!):

   ```
1. Espresso
2. Latte
3. Cappuccino
```

Puedes conectar el repositorio de GitHub añadiendo el origen remoto.

```bash
git remote add origin https://github.com/USUARIO/NOMBRE_DEL_REPOSITORIO.git
```

### Paso 3: Añadir el archivo y hacer el primer commit
Ahora que has creado tu archivo menu.txt con el menú inicial necesitamos agregarlo a Git y luego hacer el primer commit. Esto significa que estamos guardando los cambios que hemos hecho en el repositorio para poder registrarlos y poder compartirlos con otros en el futuro.

1. Añadir el archivo al área de preparación:
Para que Git registre el archivo, primero tenemos que agregarlo al área de preparación (staging area). Usamos el siguiente comando:

  ```bash
git add menu.txt
```
Este comando indica a Git que el archivo menu.txt está listo para ser guardado en el repositorio.

2. Hacer el primer commit:
Ahora que el archivo está en el área de preparación, podemos hacer un commit para registrar este cambio. Un commit es como una foto del estado de tu proyecto en ese momento.

Para hacer el commit, utiliza el siguiente comando:

  ```bash
git commit -m "Agregar menú inicial de café"

```
El texto entre comillas ("Agregar menú inicial de café") es el mensaje de commit. Este mensaje describe qué cambios has hecho. En este caso, estamos diciendo que hemos agregado el menú inicial de café.
¡Y eso es todo! Has hecho tu primer commit, guardando el estado del archivo menu.txt en tu repositorio.

### ¿Qué pasa si cometemos un error? 🧐

A veces, podemos cometer errores al escribir el mensaje de commit o al modificar un archivo. ¡No te preocupes! Git permite corregir esos errores de manera sencilla.

1. Si cometemos un error en el archivo:
Imagina que has añadido por error una receta con el nombre incorrecto en el archivo menu.txt. No hay problema. Simplemente edita el archivo para corregir el error.

Por ejemplo, si escribiste "Capuccino" en lugar de "Cappuccino", edita el archivo menu.txt y corrige el nombre.

Luego, agrega nuevamente el archivo al área de preparación y haz otro commit con un mensaje que explique la corrección:

  ```bash

git add menu.txt
git commit -m "Corregir nombre de 'Capuccino' a 'Cappuccino'"
  ```

2. Si cometemos un error en el mensaje de commit:
Si te das cuenta de que escribiste un mensaje de commit incorrecto o poco claro, puedes corregirlo fácilmente usando el comando --amend.

Si cometiste un error en el mensaje del primer commit, puedes hacer lo siguiente:

  ```bash

git commit --amend -m "Agregar menú inicial de café (corregido)"
Este comando te permite modificar el último mensaje de commit, sin tener que crear un nuevo commit. Esta una operación "destructiva", lo que significa que cambia la historia del proyecto, y esto puede ser problemático si ya se ha compartido el commit.
  ```

3. Si cometemos un error en los cambios que agregamos:
Si agregaste un archivo a la zona de preparación con git add, pero aún no has hecho el commit, puedes deshacerlo con el siguiente comando:

  ```bash

git reset menu.txt
```

Este comando quita el archivo del área de preparación, pero **no elimina** los cambios del archivo. Podrás corregirlo antes de agregarlo nuevamente.


