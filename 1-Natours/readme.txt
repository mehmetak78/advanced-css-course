Automatically compile and reload pages:

    $npm run start

    OLDER:
    Terminal 1
        $cd 1-Natours
        $npm run watch:sass
    Terminal 2
        $cd 1-Natours
        $live-server

--------------------------------------------------------------------------

- npm init

- Install npm-sass to dev dependencies
    npm install npm-sass --save-dev

- Add a script in package.json to compile scss to css
      "scripts": {
        "watch:sass": "node-sass sass/main.scss css/style.css -w"
      },

      /* you can have problem with -w flag. If so, first run without it, and then run with it */

- In the command line
    npm run watch:sass

- Install live-server globally
    npm install live-server -g

- To Run live-server (It will open the default browser and "index.html" in http://127.0.0.1:8080/)
    $cd 1-Natours
    $live-server

- A template for grid system is implemented in an other project : grid-template. Also in github. Test it there.

- Linea Icons
    https://github.com/linea-io/Linea-Iconset
    You can copy from an older project of your own
        /css/fonts
        /css/icon-font.css
    And put it into your index.html
        <link rel="stylesheet" href="css/icon-font.css">


Preparing Build Script in package.json
    $ npm install concat --save-dev
    $ npm install autoprefixer --save-dev
    $ npm install postcss-cli --save-dev
    $ npm install npm-run-all --save-dev

      "scripts": {
        "watch:sass": "node-sass sass/main.scss css/style.css -w",
        "devserver" : "live-server",
        "start": "npm-run-all --parallel devserver watch:sass",

        "compile:sass": "node-sass sass/main.scss css/style.comp.css",
        "concat:css": "concat -o css/style.concat.css css/icon-font.css css/style.comp.css",
        "prefix:css": "postcss --use autoprefixer -b 'last 10 versions'  css/style.concat.css -o css/style.prefix.css",
        "compress:css": "node-sass css/style.prefix.css css/style.css --output-style compressed",
        "build:css": "npm-run-all compile:sass concat:css prefix:css compress:css"
      },