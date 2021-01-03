# vault_ad_secret_library

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
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_ad_secret_library" {
  source = "./modules/vault/r/vault_ad_secret_library"

  # backend - (required) is a type of string
  backend = null
  # disable_check_in_enforcement - (optional) is a type of bool
  disable_check_in_enforcement = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # name - (required) is a type of string
  name = null
  # service_account_names - (required) is a type of list of string
  service_account_names = []
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The mount path for the AD backend."
  type        = string
}

variable "disable_check_in_enforcement" {
  description = "(optional) - Disable enforcing that service accounts must be checked in by the entity or client token that checked them out."
  type        = bool
  default     = null
}

variable "max_ttl" {
  description = "(optional) - The maximum amount of time, in seconds, a check-out last with renewal before Vault automatically checks it back in."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The name of the set of service accounts."
  type        = string
}

variable "service_account_names" {
  description = "(required) - The names of all the service accounts that can be checked out from this set. These service accounts must already exist in Active Directory."
  type        = list(string)
}

variable "ttl" {
  description = "(optional) - The amount of time, in seconds, a single check-out lasts before Vault automatically checks it back in."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_ad_secret_library" "this" {
  backend                      = var.backend
  disable_check_in_enforcement = var.disable_check_in_enforcement
  max_ttl                      = var.max_ttl
  name                         = var.name
  service_account_names        = var.service_account_names
  ttl                          = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_ad_secret_library.this.id
}

output "max_ttl" {
  description = "returns a number"
  value       = vault_ad_secret_library.this.max_ttl
}

output "ttl" {
  description = "returns a number"
  value       = vault_ad_secret_library.this.ttl
}

output "this" {
  value = vault_ad_secret_library.this
}
```

[top](#index)