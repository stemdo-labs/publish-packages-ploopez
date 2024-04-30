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
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

## Paso 1: Crear el archivo de flujo de trabajo

_¡Bienvenido a "Publicar paquetes"! :wave:_

Primero, tómate un momento para examinar la imagen a continuación. Muestra la relación entre _integración continua_, _entrega continua_ y _despliegue continuo_.

![](https://i.imgur.com/xZCkjmU.png)

**Integración continua** (CI) es una práctica donde los desarrolladores integran código probado en una rama compartida varias veces al día. **Entrega continua** (CD) es la siguiente fase de **integración continua** (CI) donde también nos aseguramos de empaquetar el código en una _release_ y almacenarlo en algún lugar, preferiblemente en un repositorio de artefactos. Por último, **despliegue continuo** (CD) lleva **entrega continua** (CD) al siguiente nivel al desplegar nuestras versiones directamente al mundo.

[**Docker**](https://www.docker.com/why-docker) es un motor que te permite ejecutar contenedores.
Los contenedores son paquetes de software que pueden ejecutarse de manera confiable en diferentes entornos. Los contenedores incluyen todo lo necesario para ejecutar la aplicación. Los contenedores son livianos en comparación con las máquinas virtuales. Un **Dockerfile** es un documento de texto que contiene todos los comandos e instrucciones necesarios para construir una imagen de Docker. Una **imagen de Docker** es un paquete ejecutable compuesto de código, dependencias, bibliotecas, un tiempo de ejecución, variables de entorno y archivos de configuración. Un **contenedor de Docker** es una instancia de tiempo de ejecución de una imagen de Docker.

Comenzaremos creando el archivo de flujo de trabajo para publicar una imagen de Docker en GitHub Packages.


### :keyboard: Actividad: Crear el archivo de flujo de trabajo

1. Abre una nueva pestaña del navegador y trabaja en los pasos en tu segunda pestaña mientras lees las instrucciones en esta pestaña.
1. Navega a la pestaña **Code**.
1. Desde el menú desplegable de la rama **stemdo**, haz clic en la rama **cd**.
1. Navega hasta la carpeta `.github/workflows/`, luego selecciona **Añadir archivo** y haz clic en **Crear nuevo archivo**.
1. En el campo **Nombrar tu archivo...**, ingresa `publish.yml`.
1. Agrega lo siguiente al archivo `publish.yml`:


   ```yml
   name: Publish to Docker
   on:
     push:
       branches:
         - stemdo
   permissions:
     packages: write
     contents: read
   jobs:
     publish:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v4
         # Add your test steps here if needed...
         - name: Docker meta
           id: meta
           uses: docker/metadata-action@v5
           with:
             images: ghcr.io/TU_NOMBRE/publish-packages/game
             tags: type=sha
         - name: Login to GHCR
           uses: docker/login-action@v3
           with:
             registry: ghcr.io
             username: ${{ github.repository_owner }}
             password: ${{ secrets.GITHUB_TOKEN }}
         - name: Build container
           uses: docker/build-push-action@v5
           with:
             context: .
             push: true
             tags: ${{ steps.meta.outputs.tags }}
   ```

1. Reemplaza `TU_NOMBRE` con el nombre de la organización. Recuerda que estamos usando una organización usa el nombre de la organización y agregar tu nombre como sufijo a publish-packages.
1. Asegúrate de que el nombre de la imagen sea único.
1. Haz commit a tus cambios.
1. (opcional) Crea una solicitud de extracción para ver todos los cambios que realizarás a lo largo de este curso. Haz clic en la pestaña **Pull Requests**, luego en **New pull request**, establece `base: stemdo` y `compare: cd`.
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
