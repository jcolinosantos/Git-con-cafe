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

Paso 3: Añadir la receta secreta
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
Paso 4: Volver a la rama principal
Cuando termines de trabajar en la receta nueva y quieras volver al menú principal para agregar nuevas recetas, puedes cambiar de nuevo a la rama principal (main):

  ```bash
git checkout main
  ```

Paso 5: Fusionar (merge) las ramas
Una vez que hayas probado la nueva receta y quieras añadirla al menú principal, necesitas fusionar la rama nueva_receta con la rama principal (main).

Primero, asegúrate de estar en la rama principal:

  ```bash
git checkout main
  ```
Luego, fusiona la rama nueva_receta con el siguiente comando:

  ```bash
git merge nueva_receta
  ```

Esto traerá los cambios realizados en la rama nueva_receta y los añadirá a la rama main.

Paso 6: Eliminar la rama
Si ya no necesitas la rama nueva_receta, puedes eliminarla para mantener limpio tu repositorio:

  ```bash
git branch -d nueva_receta
  ```
Esto elimina la rama localmente. Si también la habías subido a GitHub, usa este comando para eliminarla de GitHub:

  ```bash
git push origin --delete nueva_receta
  ```
Con estos pasos, has aprendido a trabajar con ramas y fusionarlas para gestionar nuevas recetas de café sin afectar el menú principal.
