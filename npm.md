# npm(1)

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



