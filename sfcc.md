# sfcc-ci(1)

  Login:

    sfcc-ci auth:login

  Realm Info:

    sfcc-ci org:list
    sfcc-ci sandbox:realm:list
    sfcc-ci org:list -j | jq -r '.[] | "\(.name) \(.realms)"'
    sfcc-ci sandbox:realm:list -r \<realm-id> --show-usage

  List all available Sandboxes:

    sfcc-ci sandbox:list

  Create new Sandbox:

    sfcc-ci sandbox:create -r \<realm-id>
    sfcc-ci sandbox:get -s \<realm-id>
    sfcc-ci sandbox:update -s \<realm-id> --ttl 0
    sfcc-ci sandbox:get -s \<realm-id> -O             # open sandbox in browser

  Sandbox Management:

    sfcc-ci sandbox:start -s \<realm-id>
    sfcc-ci sandbox:stop -s \<realm-id>
    sfcc-ci sandbox:restart -s \<realm-id>
    sfcc-ci sandbox:reset -s \<realm-id>

    sfcc-ci sandbox:delete -s \<realm-id>
    sfcc-ci sandbox:delete -s \<realm-id> --noprompt
