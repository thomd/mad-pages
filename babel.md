
# babel(1)

Babel is a JavaScript compiler

Install `babel` command line

    npm install babel-cli babel-preset-es2015

## Usage

Compile `es6-script.js`:

    ./node_modules/.bin/babel --presets es2015 es6-script.js

Create Sourcemap

    ./node_modules/.bin/babel --presets es2015 -s true es6-script.js

## REPL

    ./node_modules/.bin/babel-node --presets es2015
