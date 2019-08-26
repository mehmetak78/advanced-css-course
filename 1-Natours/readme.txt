Automatically compile and reload pages:
    Terminal 1
        $cd 1-Natours
        $npm run compile:sass
    Terminal 2
        $cd 1-Natours
        $live-server

--------------------------------------------------------------------------

- npm init

- Install npm-sass to dev dependencies
    npm install npm-sass --save-dev

- Add a script in package.json to compile scss to css
      "scripts": {
        "compile:sass": "node-sass sass/main.scss css/style.css -w"
      },

      /* you can have problem with -w flag. If so, first run without it, and then run with it */

- In the command line
    npm run compile:sass

- Install live-server globally
    npm install live-server -g

- To Run live-server (It will open the default browser and "index.html" in http://127.0.0.1:8080/)
    $cd 1-Natours
    $live-server

- A template for grid system is implemented in an other project : grid-template. Also in github. Test it there.

-