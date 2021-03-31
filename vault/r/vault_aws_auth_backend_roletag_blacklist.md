# vault_aws_auth_backend_roletag_blacklist

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
module "vault_aws_auth_backend_roletag_blacklist" {
  source = "./modules/vault/r/vault_aws_auth_backend_roletag_blacklist"

  # backend - (required) is a type of string
  backend = null
  # disable_periodic_tidy - (optional) is a type of bool
  disable_periodic_tidy = null
  # safety_buffer - (optional) is a type of number
  safety_buffer = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - Unique name of the auth backend to configure."
  type        = string
}

variable "disable_periodic_tidy" {
  description = "(optional) - If true, disables the periodic tidying of the roletag blacklist entries."
  type        = bool
  default     = null
}

variable "safety_buffer" {
  description = "(optional) - The amount of extra time that must have passed beyond the roletag expiration, before it's removed from backend storage."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_auth_backend_roletag_blacklist" "this" {
  backend               = var.backend
  disable_periodic_tidy = var.disable_periodic_tidy
  safety_buffer         = var.safety_buffer
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_aws_auth_backend_roletag_blacklist.this.id
}

output "this" {
  value = vault_aws_auth_backend_roletag_blacklist.this
}
```

[top](#index)