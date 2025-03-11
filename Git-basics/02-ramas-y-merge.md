# 3. Ramas y Merge: Gestionando las recetas de café 🌱

En Git, las **ramas** son como copias de tu proyecto donde puedes trabajar en nuevas características (como nuevas recetas de café) sin afectar el menú principal. 

### Paso 1: ¿Por qué usar ramas?

Imagina que estás creando una nueva receta de café, pero no quieres que esa receta afecte el menú principal hasta que estés listo para probarla. Las ramas permiten hacer esto de forma segura.

### Paso 2: Crear una nueva rama

Vamos a crear una nueva rama llamada 'nueva_receta' para añadir una receta sin tocar el menú principal.

```bash
git checkout -b nueva_receta
```

Esto crea una nueva rama llamada nueva_receta y te cambia a esa rama. Ahora estamos trabajando en la receta secreta sin afectar el menú principal.

### Paso 3: Añadir la receta secreta
Ahora vamos a agregar nuestra receta secreta de Flat White al archivo menu.txt:

  ```
1. Espresso
2. Latte
3. Cappuccino
4. Americano
5. Flat White
  ```
Luego, guardamos el archivo y hacemos un commit para registrar el cambio:

  ```bash
git add menu.txt
git commit -m "Añadir receta secreta de Flat White"
  ```
### Paso 4: Volver a la rama principal
Cuando termines de trabajar en la receta nueva y quieras volver al menú principal para agregar nuevas recetas, puedes cambiar de nuevo a la rama principal (main):

  ```bash
git checkout main
  ```

### Paso 5: Fusionar (merge) las ramas
Una vez que hayas probado la nueva receta y quieras añadirla al menú principal, necesitarás fusionar la rama nueva_receta con la rama principal (main). Esto se hace para combinar los cambios realizados en ambas ramas y actualizar el menú principal con la nueva receta.

Primero, asegúrate de estar en la rama principal:

  ```bash
git checkout main
  ```
Luego, fusiona la rama nueva_receta con el siguiente comando:

  ```bash
git merge nueva_receta
  ```
Este comando trae los cambios realizados en la rama nueva_receta y los integra en la rama main. Sin embargo, puede haber casos en los que Git no pueda fusionar automáticamente las ramas, esto ocurre cuando ambas ramas modifican la misma parte del mismo archivo, lo que se conoce como un conflicto de fusión.

¿Qué pasa si ocurre un conflicto de fusión?
Si Git detecta un conflicto, te mostrará un mensaje de advertencia y no completará la fusión automáticamente. En este caso, tendrás que resolver el conflicto manualmente. Git marcará las partes del archivo que están en conflicto, y tú deberás decidir cómo combinarlas.

Por ejemplo, si ambas ramas han modificado la receta de "Cappuccino", Git podría mostrar algo así en el archivo:

  ```text
<<<<<<< HEAD
1. Espresso
2. Latte
3. Cappuccino
=======
1. Espresso
2. Latte
3. Cappuccino con leche de avena
>>>>>>> nueva_receta

```
En este caso, el texto entre <<<<<<< HEAD y ======= es el contenido de la rama principal (main), y el texto entre ======= y >>>>>>> nueva_receta es el contenido de la rama nueva_receta. Debes elegir cómo deseas combinar los cambios (por ejemplo, decidir si quieres mantener "Cappuccino" o actualizarlo a "Cappuccino con leche de avena").

Una vez que hayas resuelto los conflictos, guarda el archivo y agrega los cambios:

  ```bash
git add menu.txt
  ```
Finalmente, haz un commit para completar la fusión:

  ```bash
git commit -m "Resolver conflicto de fusión y añadir receta de cappuccino con leche de avena"
  ```
Nota: Si necesitas más ayuda para resolver conflictos, Git proporciona herramientas y estrategias adicionales para facilitar este proceso. Asegúrate de revisar los cambios antes de hacer el commit final para evitar introducir errores no deseados.

### Paso 6: Eliminar la rama
Si ya no necesitas la rama nueva_receta, puedes eliminarla para mantener limpio tu repositorio:

  ```bash
git branch -d nueva_receta
  ```
Esto elimina la rama localmente. Si también la habías subido a GitHub, usa este comando para eliminarla de GitHub:

  ```bash
git push origin --delete nueva_receta
  ```
Con estos pasos, has aprendido a trabajar con ramas y fusionarlas para gestionar nuevas recetas de café sin afectar el menú principal.

### Paso 7: Crear un Pull Request (PR) para fusionar ramas de forma remota
Después de haber fusionado las ramas localmente usando el comando git merge, si estás trabajando en un proyecto colaborativo o prefieres gestionar las fusiones de manera más controlada, el siguiente paso es crear un Pull Request (PR) en GitHub.

Un Pull Request (PR) es una solicitud para que otros colaboradores revisen los cambios antes de fusionarlos en la rama principal del repositorio. Es una excelente manera de revisar el código, resolver posibles conflictos y asegurarse de que todo esté en orden antes de hacer la fusión final.

¿Cómo crear un Pull Request?
1. Sube tus cambios a GitHub: Si aún no has subido tus cambios al repositorio remoto, primero deberás empujar (push) tu rama con los cambios al repositorio de GitHub.

  ```bash
git push origin main
  ```
2. Abrir un Pull Request en GitHub:

*  Ve a tu repositorio en GitHub.
*  Verás un aviso que te sugiere abrir un Pull Request después de subir tu rama. Si no lo ves, puedes ir a la pestaña Pull Requests en la parte superior del repositorio y hacer clic en New Pull Request.
*  Selecciona la rama que deseas fusionar (en este caso, nueva_receta) y la rama principal (main) como destino de la fusión.
*  Agrega un título y una descripción para tu PR, detallando los cambios realizados (por ejemplo, “Añadir nueva receta de café: Flat White”).
3. Revisar y fusionar: Una vez que hayas abierto el PR, otros colaboradores podrán revisar tu código. Si todo está correcto y no hay conflictos, puedes proceder con la fusión directamente desde la interfaz de GitHub, haciendo clic en Merge pull request.

4. Eliminar la rama (opcional): Después de fusionar el PR, puedes eliminar la rama remota (nueva_receta) para mantener el repositorio limpio. GitHub te dará la opción de eliminarla automáticamente al realizar la fusión.

Nota: El uso de Pull Requests es especialmente útil cuando se trabaja con varios colaboradores en un proyecto, ya que permite que todos revisen y aprueben los cambios antes de integrarlos en la rama principal. Además, GitHub ofrece herramientas para realizar revisiones de código, discutir cambios y realizar mejoras antes de fusionar.


