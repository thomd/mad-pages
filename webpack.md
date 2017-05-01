
# webpack(1)

## Setup

File Structure:

    ├── app
    │   └── main.js
    ├── build
    │   └── index.html
    ├── package.json
    └── webpack.config.js

Install:

    npm init -y
    npm install --save-dev webpack webpack-dev-server

Add _npm script_:

    "scripts": {
      "build": "webpack",
        "dev": "webpack-dev-server --devtool eval --progress --colors --hot --content-base build"
    }

## Configuration

_webpack.config.js_:

    module.exports = {
       entry: './app',
       output: {
          path: 'build',
          filename: 'bundle.js'
       }
    }

## Source map

_webpack.config.js_:

      devtool: 'source-map'

## ES6

    npm i -D babel-loader babel-core babel-preset-es2015

_webpack.config.js_:

      module: {
        loaders: [
          {
            test: /\.js/,
            include: __dirname + '/src',
            loader: 'babel',
            query: {
              presets: ['es2015']
            }
          }
        ]
      }

## CSS Styles

    npm i -D css-loader style-loader

_webpack.config.js_:

      module: {
        loaders: [
          {
            test: /\.css/,
            include: __dirname + '/src',
            loaders: ['style', 'css']
          }
        ]
      }

