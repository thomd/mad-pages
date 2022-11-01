# az(1)

    az login --use-device-code
    az account show
    az account show --query id --output tsv                       # get subscription ID

## Resource Groups

    az account list-locations -o table                            # list possible locations
    az group list -o table
    az group create -n \<group> -l \<location>
    az group delete -n \<group> --no-wait -y
