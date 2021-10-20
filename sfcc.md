# sfcc-ci(1)

  Login:

    sfcc-ci auth:login

  Realm Info:

    sfcc-ci org:list
    sfcc-ci sandbox:realm:list
    sfcc-ci org:list -j | jq -r '.[] | "\(.name) \(.realms)"'
    sfcc-ci sandbox:realm:list -r \<realm-id> --show-usage

  List Sandboxes:

    sfcc-ci sandbox:list

  Create new Sandbox:

    sfcc-ci sandbox:create -r \<realm-id>
    sfcc-ci sandbox:get -s \<sbx-id>
    sfcc-ci sandbox:update -s \<sbx-id> --ttl 0
    sfcc-ci sandbox:get -s \<sbx-id> -O             # open sandbox in browser

  Sandbox Management:

    sfcc-ci sandbox:start -s \<sbx-id>
    sfcc-ci sandbox:stop -s \<sbx-id>
    sfcc-ci sandbox:restart -s \<sbx-id>
    sfcc-ci sandbox:reset -s \<sbx-id>

    sfcc-ci sandbox:delete -s \<sbx-id>
    sfcc-ci sandbox:delete -s \<sbx-id> --noprompt
