# DS Terraform

This repository contains Terraform files to provision services in Azure personal account.

## Pre-requisites

## CI/CD Pipeline

### Steps

# Local Development Setup
## Prerequisites
You will need to install the following tools:
* [Terraform](https://www.terraform.io/downloads)
* [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-windows)  

## Backend Configuration
Create a `config.tfbackend` file in the same directory as `backend.tf`. Populate `config.tfbackend` with arguements that would normally be in the backend block. It should look something like this:
```
subscription_id = "aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa"
resource_group_name = "ds-terraform-states"
storage_account_name = "dstfstateallenvs"
container_name = "tf-eastus-np"
key = "tf.state"
tenant_id = "aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa"
client_id = "aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa"
client_secret = "asdf.asdf"
```
## Running Terraform
You will need to run `terraform init` if this is your first time running terraform or whenever there is change in the backend configuration.
``` bash
terraform init -backend-config=config.tfbackend
```
Now you can run any terraform command.
``` bash
terraform apply -var-file=config/eastus-prod.tfvars
```

### Contact Details

Dmitry Sandovich (dsandovich@gmail.com)