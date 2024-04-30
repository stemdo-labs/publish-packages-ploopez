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
  <<< Notas del autor: Paso 4 >>>
  Comienza este paso reconociendo el paso anterior.
  Define términos y enlaza a docs.github.com.
-->

## Paso 4: Extrae tu imagen

_¡Ahora las cosas están en marcha! :sparkles:_

¡Vaya, ahora las cosas están en marcha! Esto puede tomar unos minutos. Esto podría llevar un poco de tiempo, así que toma tus palomitas :popcorn: y espera a que termine la construcción antes de continuar.

Para extraer la imagen de Docker, primero necesitamos iniciar sesión en Docker.

Antes de que podamos usar esta imagen de Docker, deberás generar un [token de acceso personal](https://docs.github.com/es/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) que contenga los siguientes permisos:

- repo (todo)
- write:packages
- read:packages

![captura de pantalla de la página de creación de token de acceso personal con casillas para repo (todo), write:packages y read:packages marcadas](https://user-images.githubusercontent.com/3250463/219254714-82bb1da5-33b1-491b-97c0-b25f51494f6a.png)

Utilizaremos este token para iniciar sesión en Docker y autenticarnos con el paquete.

1. Abre tu terminal (se recomienda Bash o Git Bash).
1. Utiliza el siguiente comando para iniciar sesión:
   ```bash
   docker login ghcr.io -u NOMBRE_DE_USUARIO
   ```
1. Reemplaza ``NOMBRE_DE_USUARIO`` con tu nombre de usuario de GitHub.
1. Ingresa tu nuevo Token de Acceso Personal como contraseña.
1. Presiona **Enter**.

Si todo salió bien, :crossed_fingers: deberías ver ``Login Succeeded`` en tu terminal.


### :keyboard: Actividad: Extraer tu imagen

1. Copia y pega el comando `pull` de las instrucciones del paquete en tu terminal. Debería verse algo como esto:
   - `docker pull ghcr.io/NOMBRE_DE_ORGANIZACION/publish-packages/game:TAG`
     ![captura de pantalla del comando pull en la página del paquete GitHub](https://user-images.githubusercontent.com/3250463/219254981-9ff949fa-4d01-46e3-9e3d-b8ce3710c2a9.png)
   - _Consejo: Para llegar a esta página, haz clic en la pestaña **Code** en la parte superior de tu repositorio. Luego, encuentra la barra de navegación debajo de la descripción del repositorio y haz clic en el enlace del encabezado **Packages**_
1. Reemplaza `NOMBRE_DE_ORGANIZACION` con tu nombre de tu organización.
1. Reemplaza `TAG` con la etiqueta de la imagen.
1. Presiona **Enter**.
1. Deberías ver una salida que indique que la extracción fue exitosa, como `Status: Downloaded newer image for ghcr.io/NOMBRE_DE_ORGANIZACION/publish-packages/game:TAG`.
   ![captura de pantalla de la salida exitosa de la imagen Docker](https://user-images.githubusercontent.com/3250463/219255178-3c943a6f-6c15-4f59-9002-228249b1c469.png)
1. _No podemos verificar automáticamente este paso por ti, ¡así que por favor continúa con el siguiente paso a continuación!_

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
<!--
  <<< Notas del autor: Finalizar >>>
  Revisa lo que aprendimos, solicita comentarios, proporciona los siguientes pasos.
-->

## Finalizar

_¡Felicidades amigo, has completado este curso!_

<img src=https://octodex.github.com/images/collabocats.jpg alt=celebrate width=300 align=right>

Aquí tienes un resumen de todas las tareas que has realizado en tu repositorio:

- Escribiste un flujo de trabajo que envía un código a través de un canal de entrega continua.
- Construiste un artefacto totalmente desplegable.
- ¡Lo hiciste usando GitHub Actions y GitHub Packages!

### ¿Qué sigue?

- Publica tus propios paquetes desde tus proyectos.
- Nos encantaría saber qué opinas de este curso [en nuestro foro de discusión](https://github.com/orgs/skills/discussions/categories/publish-packages).
- [Toma otro curso de GitHub Skills](https://github.com/skills).
- [Lee la documentación de GitHub Getting Started](https://docs.github.com/en/get-started).
- Para encontrar proyectos a los que contribuir, echa un vistazo a [GitHub Explore](https://github.com/explore).

<footer>

<!--
  <<< Notas del autor: Pie de página >>>
  Agrega un enlace para obtener soporte, página de estado de GitHub, código de conducta, enlace de licencia.
-->

---

Obtén ayuda: [Publica en nuestro foro de discusión](https://github.com/orgs/skills/discussions/categories/test-with-actions) &bull; [Revisa la página de estado de GitHub](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Código de Conducta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [Licencia MIT](https://gh.io/mit)

</footer>
