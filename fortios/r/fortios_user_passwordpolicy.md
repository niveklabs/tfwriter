# fortios_user_passwordpolicy

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_passwordpolicy" {
  source = "./modules/fortios/r/fortios_user_passwordpolicy"

  # expire_days - (optional) is a type of number
  expire_days = null
  # name - (optional) is a type of string
  name = null
  # warn_days - (optional) is a type of number
  warn_days = null
}
```

[top](#index)

### Variables

```terraform
variable "expire_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "warn_days" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_passwordpolicy" "this" {
  expire_days = var.expire_days
  name        = var.name
  warn_days   = var.warn_days
}
```

[top](#index)

### Outputs

```terraform
output "expire_days" {
  description = "returns a number"
  value       = fortios_user_passwordpolicy.this.expire_days
}

output "id" {
  description = "returns a string"
  value       = fortios_user_passwordpolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_user_passwordpolicy.this.name
}

output "warn_days" {
  description = "returns a number"
  value       = fortios_user_passwordpolicy.this.warn_days
}

output "this" {
  value = fortios_user_passwordpolicy.this
}
```

[top](#index)