
<!--
  <<< Notas del autor: Paso 5 >>>
  Comienza este paso reconociendo el paso anterior.
  Define términos y enlaza a docs.github.com.
-->

## Paso 5: Ejecuta tu imagen

_¡Bien hecho al obtener tu imagen Docker! :relaxed:_

Intentemos ejecutarla.

### :keyboard: Actividad: Ejecuta tu imagen

1. Encuentra la información de tu imagen escribiendo `docker image ls`.
   ![captura de pantalla de la salida del comando Docker image ls: lista las imágenes de Docker, REPOSITORY TAG y URL de Docker](https://i.imgur.com/UAwRXiq.png)<!-- Esta captura de pantalla debe cambiarse. -->
1. Utiliza el siguiente comando para ejecutar un contenedor desde tu imagen:
   ```bash
   docker run -dp 8080:80 --rm <YOUR_IMAGE_NAME:TAG>
   ```
1. Reemplaza `YOUR_IMAGE_NAME` con el nombre de tu imagen bajo la columna `REPOSITORY`.
1. Reemplaza `TAG` con la etiqueta de la imagen bajo la columna `TAG`.
1. Presiona **Enter**.
1. Si todo salió bien, verás un valor hash como salida en tu pantalla.
1. Opcionalmente, puedes abrir [localhost:8080](http://localhost:8080) para ver la página que acabas de crear.
1. _No podemos verificar automáticamente este paso por ti, ¡así que por favor continúa con el siguiente paso a continuación!_
