<!--
  <<< Notas del autor: Paso 2 >>>
  Comienza este paso reconociendo el paso anterior.
  Define términos y enlaza a docs.github.com.
-->

## Paso 2: Agregar un Dockerfile

_¡Has creado un flujo de trabajo de publicación! :tada:_

Añadiremos un `Dockerfile` a la rama `cd`. El `Dockerfile` contiene un conjunto de instrucciones que se almacenan en una `Imagen de Docker`. Si deseas, puedes [aprender más sobre Dockerfiles](https://docs.docker.com/engine/reference/builder/).

### :keyboard: Actividad: Agregar un Dockerfile

1. En la rama `cd`, crea un archivo `Dockerfile` en la raíz del proyecto e incluye:
   ```dockerfile
   FROM nginx:1.24-alpine
   COPY . /usr/share/nginx/html
   ```

1. Haz commit a tus cambios.
1. Espera aproximadamente 20 segundos y luego actualiza esta página (la que estás siguiendo las instrucciones). [GitHub Actions](https://docs.github.com/en/actions) se actualizará automáticamente al siguiente paso.
