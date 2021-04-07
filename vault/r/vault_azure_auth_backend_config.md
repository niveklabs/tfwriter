# vault_azure_auth_backend_config

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
module "vault_azure_auth_backend_config" {
  source = "./modules/vault/r/vault_azure_auth_backend_config"

  # backend - (optional) is a type of string
  backend = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # environment - (optional) is a type of string
  environment = null
  # resource - (required) is a type of string
  resource = null
  # tenant_id - (required) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional) - Unique name of the auth backend to configure."
  type        = string
  default     = null
}

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

variable "environment" {
  description = "(optional) - The Azure cloud environment. Valid values: AzurePublicCloud, AzureUSGovernmentCloud, AzureChinaCloud, AzureGermanCloud."
  type        = string
  default     = null
}

variable "resource" {
  description = "(required) - The configured URL for the application registered in Azure Active Directory."
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
resource "vault_azure_auth_backend_config" "this" {
  # backend - (optional) is a type of string
  backend = var.backend
  # client_id - (optional) is a type of string
  client_id = var.client_id
  # client_secret - (optional) is a type of string
  client_secret = var.client_secret
  # environment - (optional) is a type of string
  environment = var.environment
  # resource - (required) is a type of string
  resource = var.resource
  # tenant_id - (required) is a type of string
  tenant_id = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_azure_auth_backend_config.this.id
}

output "this" {
  value = vault_azure_auth_backend_config.this
}
```

[top](#index)