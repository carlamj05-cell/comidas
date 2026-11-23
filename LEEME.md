# COMIDAS (versión web)

Web gratuita de COMIDAS. Se abre desde cualquier navegador (Chrome, Safari...) sin cuenta de Claude. Cada persona entra con su cuenta de Google o con correo y contraseña, y tiene sus propios datos.

- Datos e inicio de sesión: Firebase (Google), plan gratuito Spark.
- Web: GitHub Pages, gratis.

## Archivos

| Archivo | Para qué |
|---|---|
| index.html | La app |
| config.js | Los datos de tu proyecto de Firebase (lo rellenas tú) |
| firestore.rules | Reglas de seguridad: cada persona solo ve lo suyo |
| manifest.webmanifest, icon*.png, icon.svg | Icono y modo app al añadirla a la pantalla de inicio |

## 1. Crear el proyecto de Firebase (10 min)

1. Entra en https://console.firebase.google.com con tu cuenta de Google y crea un proyecto (por ejemplo "comidas"). Google Analytics no hace falta.
2. **Authentication** > Comenzar > Método de inicio de sesión: activa **Google** y **Correo electrónico/contraseña**.
3. **Firestore Database** > Crear base de datos. Ubicación: `europe-southwest1` (Madrid). Modo producción.
4. En Firestore, pestaña **Reglas**: borra lo que haya, pega el contenido de `firestore.rules` y pulsa Publicar.
5. Rueda dentada > **Configuración del proyecto** > General > Tus apps > icono web `</>`. Ponle de nombre COMIDAS (no marques Hosting). Copia los valores de `firebaseConfig` en `config.js`.

## 2. Publicar la web en GitHub Pages (5 min)

1. Crea una cuenta en https://github.com si no tienes.
2. New repository > nombre `comidas` > Public > Create.
3. "uploading an existing file": arrastra todos los archivos de esta carpeta (los archivos, no la carpeta) > Commit changes.
4. Settings > Pages > Source: Deploy from a branch > Branch `main` y carpeta `/ (root)` > Save.
5. En 1-2 minutos la web está en `https://TU-USUARIO.github.io/comidas/`.

## 3. Autorizar la dirección en Firebase

Firebase > Authentication > Settings > **Authorized domains** > Add domain: `TU-USUARIO.github.io`.

## 4. Pasar tus datos

1. En COMIDAS de Claude: Más > Pasar a la web > Descargar mis datos.
2. En la web: entra con tu cuenta > Más > Cuenta y datos > Importar datos > elige el archivo > Importar.

## 5. Ponerla como app en el móvil

- iPhone (Safari): Compartir > Añadir a pantalla de inicio.
- Android (Chrome): menú ⋮ > Añadir a pantalla de inicio (o Instalar app).

Si en el iPhone, abierta desde el icono de la pantalla de inicio, no te deja entrar con Google, entra con correo y contraseña.

## Compartir

Pasa la dirección a quien quieras. Cada persona crea su cuenta y empieza vacía. Si quieres que empiece con tu recetario, descarga tus datos y pásale el archivo: al importar puede marcar solo "Recetario" (y lo que quiera).

## Cambios

- Para cambiar la app: sube el `index.html` nuevo al repositorio (Add file > Upload files) y en un minuto está actualizada.
- Para que Claude prepare un menú nuevo: descarga tus datos, pásale el archivo y te devuelve otro para importar.

## Límites gratuitos

Firebase Spark: 50.000 lecturas y 20.000 escrituras al día y 1 GB de datos. Cada vez que se abre la app lee unos 150 registros, así que hay margen de sobra para ti y para la gente con la que la compartas.
