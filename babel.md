
# babel(1)

Babel is a JavaScript compiler

Install `babel` command line

    npm install babel-cli babel-preset-es2015

## Usage

Compile `script.js`:

    babel --presets es2015 script.js

Create Sourcemap

    babel --presets es2015 -s true script.js

Node REPL

    babel-node --presets es2015 script.js
