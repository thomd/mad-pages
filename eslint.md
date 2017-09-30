
# eslint(1)

## Quickstart

    npm init -y
    npm i eslint
    npx eslint --init
    npx eslint "\*\*/*.js"
    npx eslint "\*\*/*.js" --fix
    npx eslint "\*\*/*.js" --format=codeframe|html 

## Configuration

  Create configuration

    npx eslint --init

  or start with __Standard__ configuration

    npm i eslint-config-standard eslint-plugin-node eslint-plugin-promise eslint-plugin-standard

    # .eslintrc.yml
    extends: standard

