
# SASS

## Setup

    npm init -y
    npm i -D node-sass
    npm i -D stylelint stylelint-config-sass-guidelines
    npm i -D onchange

Create a `.stylelintrc` file:

    {
      "extends": "stylelint-config-sass-guidelines"
    }

Create a `package.json` for npm scripts:

    {
      "scripts": {
        "sass": "node-sass --output css --output-style expanded scss",
        "sass:lint": "stylelint scss/*.scss",
        "css": "npm run sass:lint && npm run sass",
        "css:watch": "onchange scss/*.scss -- npm run css"
      }
    }

Sass-files are in a `scss` folder, CSS-files will be compiled into a `css` folder with

    npm run -s css
    npm run -s css:watch

## API

