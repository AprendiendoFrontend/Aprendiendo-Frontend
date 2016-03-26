## Sesión 3 - Frontend Boilerplate basado en NPM

#### Instalación de Node-sass
Inicializamos un proyecto NPM mediante

```
$ npm init
```

· Nos genera un archivo `package.json` con toda la meta-información del proyecto.
. Instalamos las aplicaciones de forma local y las referenciamos como dependencias de desarrollo:

```
$ npm install node-sass --save-dev
```

Un modo abreviado de hacer lo mismo sería:

```
$ npm i node-sass -D
```

### Creamos la estructura de directorios
Nuestro proyecto tendrá unas carpetas que contendrá los archivos fuente y otra de distribución. La estructura será:

```
.
├── dist
│   ├── css
│   │   └── main.css
│   └── index.html
├── package.json
└── src
    └── scss
        └── main.scss
```


### Añadimos un script para preprocesar nuestros archivos Sass:
El Script `css` utiliza `node-sass` para preprocesar los archivos de la carpeta `src/scss` guardándolos en `dist/css` con el estilo comprimido. Además añadimos meta-datos mediante `source-map-embed` que nos ayudan a debuggar nuestro código.

```
"scripts": {
  "css": "node-sass -o dist/css src/scss --output-style compressed --source-map-embed"
}
```

### Instalamos OnChange
Mediante `onchange` crearemos una tarea de *watching** que vuelva a preprocesar de forma automática los archivos SCSS cada vez que los modificamos.

```
$ npm install onchange --save-dev
```

Ahora ya podemos referenciarla en la key "scripts":

```
"watch:css": "onchange src/scss/*.scss -- npm run css"
```

En este *script* estamos vigilando los cambios que se produzcan en cualquier archivo con extensión `.scss` dentro de la carpeta `src/scss` y una vez que se produce dicho cambio lanzamos la tarea `npm run css`.

### Instalamos browser-sync
Para no tener que recargar el navegador manualmente con cada cambio, añadimos browser-sync a nuestro Boilerplate:

```
$ npm install browser-sync --save-dev
```

Y creamos un script para ejecutarlo al que llamaremos `serve`:

```
"serve": "browser-sync start --server dist --files dist",
```

### Parallelshell
La tarea de `watching` se queda con el *prompt*. Para poder ejecutar varios scripts de NPM de forma simultanea instalaremos `Parallelshell`

```
$ npm install parallelshell --save-dev
```

Y la ejecutaremos mediante el *script* `dev`:

```
"dev": "parallelshell 'npm run watch:css' 'npm run serve'"
```
