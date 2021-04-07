# vault_terraform_cloud_secret_backend

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
module "vault_terraform_cloud_secret_backend" {
  source = "./modules/vault/r/vault_terraform_cloud_secret_backend"

  # address - (optional) is a type of string
  address = null
  # backend - (optional) is a type of string
  backend = null
  # base_path - (optional) is a type of string
  base_path = null
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # token - (optional) is a type of string
  token = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional) - Specifies the address of the Terraform Cloud instance, provided as \"host:port\" like \"127.0.0.1:8500\"."
  type        = string
  default     = null
}

variable "backend" {
  description = "(optional) - Unique name of the Vault Terraform Cloud mount to configure"
  type        = string
  default     = null
}

variable "base_path" {
  description = "(optional) - Specifies the base path for the Terraform Cloud or Enterprise API."
  type        = string
  default     = null
}

variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration for secrets in seconds"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration for secrets in seconds"
  type        = number
  default     = null
}

variable "token" {
  description = "(optional) - Specifies the Terraform Cloud access token to use."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_terraform_cloud_secret_backend" "this" {
  # address - (optional) is a type of string
  address = var.address
  # backend - (optional) is a type of string
  backend = var.backend
  # base_path - (optional) is a type of string
  base_path = var.base_path
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  # description - (optional) is a type of string
  description = var.description
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = var.max_lease_ttl_seconds
  # token - (optional) is a type of string
  token = var.token
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_backend.this.id
}

output "this" {
  value = vault_terraform_cloud_secret_backend.this
}
```

[top](#index)