# az(1)

## Login using AAD/MSA Identity

    az login                                           # interactive login via webpage
    az login --use-device-code                         # interactive login via webpage manually via https://microsoft.com/devicelogin if no web browser is available
    az login -u \<username> -p \<password>               # explicit login via credentials

    az account list -o table                           # list Azure accounts
    az account set -s \<account-name>                   # set default azure account / subscription
    az account show -o table                           # show account info

## Login using PAT Token

Create a PAT token in Azure DevOps > User Settings > Security > Personal Access Tokens

    az devops login                                    # you are asked to enter the PAT via console

## Resource Groups

    az account list-locations -o table                 # list possible locations
    az group list -o table
    az group create -n \<group> -l \<location>
    az group delete -n \<group> --no-wait -y

# Azure DevOps

    az pipelines list -p "$AZDO_PROJECT" -o table
