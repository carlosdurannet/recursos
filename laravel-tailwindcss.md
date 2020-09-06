## Usar Tailwind CSS con Laravel
### Instalar Tailwind CSS
```
npm install --save-dev tailwindcss laravel-mix-tailwind
npx tailwindcss init
```
### Activar Tailwind CSS
Editar el fichero **webpack.mix.js** con el siguinte contenido:

```
const mix = require('laravel-mix');
require('laravel-mix-tailwind');

/*
 |--------------------------------------------------------------------------
 | Mix Asset Management
 |--------------------------------------------------------------------------
 |
 | Mix provides a clean, fluent API for defining some Webpack build steps
 | for your Laravel application. By default, we are compiling the Sass
 | file for the application as well as bundling up all the JS files.
 |
 */

mix.js('resources/js/app.js', 'public/js')
    .sass('resources/sass/app.scss', 'public/css')
    .tailwind();

```
Elminar el fichero **resources/sass/_variables.scss** (si existe). 

En el fichero **resources/sass/app.scss** eliminar la importación del fichero anterior y la de bootstrap (si existieran) e incluir Tailwind CSS con las siguientes líneas
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
### Compilar Tailwind CSS
Ejecutar el comando:
```
npm run watch
```
Si al ejecutar este comando surge el siguiente error:
```
Error: Specified Tailwind config file "[ruta/del/proyecto]/tailwind.js" doesn't exist.
```
Renombrar el fichero **tailwind.config.js** por **tailwind.js**



 
