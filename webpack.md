
# webpack(1)

## Setup

    npm install --save-dev webpack

Add _npm script_:

    "scripts": {
      "build": "webpack"
    }

File Structure:

    .
    ├── app
    │   └── main.js
    ├── build
    │   └── index.html
    ├── package.json
    └── webpack.config.js

## Configuration

_webpack.config.js_:

    var path = require('path')
    module.exports = {
       entry: path.resolve(__dirname, 'app/main.js'),
       output: {
          path: path.resolve(__dirname, 'build'),
          filename: 'bundle.js',
       }
    }
