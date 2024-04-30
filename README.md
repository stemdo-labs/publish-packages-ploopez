<header>

<!--
  <<< Notas del autor: Encabezado del curso >>>
  Incluye una imagen de 1280×640, el título del curso en caso de oración y una descripción concisa en énfasis.
  En la configuración de tu repositorio: habilita el repositorio de plantillas, agrega tu imagen social de 1280×640, elimina automáticamente las ramas principales.
  Agrega tu licencia de código abierto, GitHub utiliza la licencia MIT.
-->

# Publicar en GitHub Packages

_Utiliza GitHub Actions para publicar tu proyecto en una imagen Docker._

</header>

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

<footer>

<!--
  <<< Notas del autor: Pie de página >>>
  Agrega un enlace para obtener soporte, página de estado de GitHub, código de conducta, enlace de licencia.
-->

---

Obtén ayuda: [Publica en nuestro foro de discusión](https://github.com/orgs/skills/discussions/categories/test-with-actions) &bull; [Revisa la página de estado de GitHub](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Código de Conducta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [Licencia MIT](https://gh.io/mit)

</footer>
