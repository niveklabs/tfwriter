# vault_azure_secret_backend

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_azure_secret_backend" {
  source = "./modules/vault/r/vault_azure_secret_backend"

  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # description - (optional) is a type of string
  description = null
  # environment - (optional) is a type of string
  environment = null
  # path - (optional) is a type of string
  path = null
  # subscription_id - (required) is a type of string
  subscription_id = null
  # tenant_id - (required) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "client_id" {
  description = "(optional) - The client id for credentials to query the Azure APIs. Currently read permissions to query compute resources are required."
  type        = string
  default     = null
}

variable "client_secret" {
  description = "(optional) - The client secret for credentials to query the Azure APIs"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "environment" {
  description = "(optional) - The Azure cloud environment. Valid values: AzurePublicCloud, AzureUSGovernmentCloud, AzureChinaCloud, AzureGermanCloud."
  type        = string
  default     = null
}

variable "path" {
  description = "(optional) - Path to mount the backend at."
  type        = string
  default     = null
}

variable "subscription_id" {
  description = "(required) - The subscription id for the Azure Active Directory."
  type        = string
}

variable "tenant_id" {
  description = "(required) - The tenant id for the Azure Active Directory organization."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_azure_secret_backend" "this" {
  client_id       = var.client_id
  client_secret   = var.client_secret
  description     = var.description
  environment     = var.environment
  path            = var.path
  subscription_id = var.subscription_id
  tenant_id       = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_azure_secret_backend.this.id
}

output "this" {
  value = vault_azure_secret_backend.this
}
```

[top](#index)