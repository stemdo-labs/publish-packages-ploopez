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
