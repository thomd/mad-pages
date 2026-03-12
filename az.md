# az(1)

## Authentication

    az account list -o table
    az account list | jq '.[] | select(.isDefault==true) | .name'       # name of default account

COMPANY: login to company account via OAuth ( --use-device-code is disabled for our company accounts)

    az login

PRIVATE: login to private account via device code in browser

    az login --use-device-code


