# Introducción a Vue

Este es el repositorio de mis prácticas y aprendizajes con Vue, mis conocimientos y experiencias estarán en este repositorio.
Vue es un framework progresivo para construir interfaces de usuario.

## Prerrequisitos

Debes tener conocimientos previos de:

- [Introducción a HTML](https://github.com/Sam24Hernandez/html-tutorial).
- [Introducción a CSS](https://github.com/Sam24Hernandez/css-tutorial).
- [Introducción a Javascript](https://github.com/Sam24Hernandez/javascript-tutorial).

- **Node**: React requiere una versión LTS actual, activa o de mantenimiento de Node.js, en caso de instalarlo con npm.

Para más información sobre la instalación de Node.js, ver [nodejs.org](https://nodejs.org/es/). Si no está seguro de qué versión de Node.js se ejecuta en su sistema, ejecute `node -v` en una ventana terminal.

### ¿Qué herramientas necesitarás?

Para obtener la mejor experiencia de usuario y desarrollador use una cadena de herramientas integrada.

- **Inclusión Directa con `<script>`**: Simplemente descargue e incluya la etiqueta script con la ruta correcta. Vue será registrado como una variable global.

`<script src="https://cdn.jsdelivr.net/npm/vue@2.5.16/dist/vue.js"></script>`

Puede examinar el código fuente del paquete [NPM](cdn.jsdelivr.net/npm/vue).

- **NPM**: NPM es el método de instalación recomendado para construir aplicaciones a gran escala con Vue. Este combina perfectamente con empaquetadores de módulos, tales como Webpack o Browserify.

`npm install vue`

- **Navegadores web, para probar el código**: Actualmente los navegadores más usados son Firefox, Chrome, Opera, Safari, Vivaldi, Brave.

### Correr la Aplicación en el navegador

1. Instala @vue/cli, una herramienta que hará que nuestro arranque sea mucho más fácil.

`yarn global add @vue/cli`

`npm install -g @vue/cli`

2. Para crear un proyecto con la herramienta Vue CLI, desplazate en tu directorio de proyecto y ejecuta:

`vue create myApp`

3. Después de crear el proyecto, dirigete al proyecto creado y ejecuta:

`yarn serve`

O

`npm run serve`

Abre automáticamente en tu navegador a http://localhost:8080/.
