
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

## Disable Rules with Inline Comments

To completely ignore a whole file, put this on top of file:

    /\* eslint-disable \*/

To ignore a specific eslint rule by line

    /\* eslint no-var: 0 \*/
    var foo = true;

To ignore eslint by line:

    // eslint-disable-next-line
    var foo = true;

  or

    var foo = true;  // eslint-disable-line


