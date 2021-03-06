# Setup Terraform with an Azure backend

This repo contains a Github action to setup the resources for Terraform with an
Azure backend. 

The action creates a resource group, a storage account and a container to keep
the Terraform state in. It needs a service principal with sufficient
permissions to create the mentioned resources.

## Service principal
Create the service principal with the following command:

```bash
az ad sp create-for-rbac \
    --name <service principal name> \
    --sdk-auth \
    --role "Contributor" \
    --scopes /subscriptions/<subscription id>
```
