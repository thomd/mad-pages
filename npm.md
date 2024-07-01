# npm(1)

## Install

    npm install --no-fund --no-audit \<package>

## Linking

  Link

    cd /path/to/local/node/module/foo
    npm link
    cd /path/to/project
    npm link foo

  Unlink

    cd /path/to/local/node/module/foo
    npm unlink
    cd /path/to/project
    npm unlink foo

## Versioning

  bump version based on semver in _package.json_, sets git tag and commits:

    npm version major | minor | patch            # bump version, set git tag and commit
    npm version minor -m "Upgrade to %s"         # bump version with custom commit message

## List Packages

    npm list -g --depth 0                        # list globally installed packages

# npm-check(1)

    npx npm-check
    npx npm-check -u                   # interactive update
    npx npm-check -g                   # look for global modules
