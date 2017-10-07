

# xo(1)

    npm i xo
    npx xo --init
    npx xo --fix
    npx xo src/\*\*/\*.js

    npx xo --no-semicolon --space
    npx xo --cwd src                                    // lint all files in `src/`
    npx xo --reporter=codeframe                         // more details
    npx xo --env=es6

  Use `--env` for pre-defined global variables.
  Envs are the same as in _ESLint_: `browser`, `node` (default), `commonjs`, `jquery`, `es6`, `mocha`, ...

    npx xo --plugin=html --extension=html               // lint inline javascript in html (`npm i eslint-plugin-html`)

## package.json

    {
      "scripts": {
        "lint": "xo",
        "precommit": "npm run xo"                  // npm i husky
      },
      "xo": {
        "envs": ["browser", "jquery"],
        "semicolon": false,
        "space": true
      }
    }
