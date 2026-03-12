# az(1)

## Authentication

    az account list -o table
    az account list | jq '.[] | select(.isDefault==true) | .name'       # name of default account

COMPANY: login to company account via OAuth ( --use-device-code is disabled for our company accounts)

    az login

PRIVATE: login to private account via device code in browser

    az login --use-device-code

Logout:

    az logout --username EMAIL

## Subscription

    az account set -s SUBSCRIPTION                                      # set default subscription
    az account show                                                     # details of the default subscription
    az account show -s SUBSCRIPTION                                     # details of subscription SUBSCRIPTION
