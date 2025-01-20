# npx(1)

## Examples

    npx alex README.md                                   # check text for insensitive or inconsiderate writing

    npx http-server                                      # run a static web server in your current directory
    npx json-server data.json                            # run a mock REST API server
    echo -e "\033[33m hello" | npx strip-ansi-cli        # remove terminal color codes from piped text

    npx sort-package-json                                # sort your package.json keys
    npx nsp check                                        # scan your npm project for vulnerabilities and security alerts
    npx npm-check                                        # interactively update npm dependencies
    npx npm-check --skip-unused --update

    npx npkill                                           # finds and removes old and heavy `node_modules` folders

  Fun `fun` fun

    npx figlet-cli text                                  # ascii text generator
    echo hello | npx lolcatjs                            # colorful rainbow text
    npx firew0rks                                        # ascii firework
    npx firew0rks fireplace -1                           # ascii fireplace
    npx benny-hill npm install                           # play Benny Hill music while running a command
    npx qrip https://example.com                         # generate QR code

  PlantUML

    npx --package node-plantuml puml generate --unicode --text "A -> B: Hello"

  Export medium stories

    npx mediumexporter \<medium-url> > file.md            # export a medium story to markdown
    npx mediumexporter \<medium-url> | glow -             # export a medium story to terminal

  Make any web page a desktop application

    npx nativefier web.whatsapp.com
    npx nativefier teams.microsoft.com --internal-urls '(.*?)' -n "Microsoft Teams" -p linux
