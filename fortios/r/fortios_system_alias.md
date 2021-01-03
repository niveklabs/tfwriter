# fortios_system_alias

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
module "fortios_system_alias" {
  source = "./modules/fortios/r/fortios_system_alias"

  # command - (optional) is a type of string
  command = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "command" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_alias" "this" {
  command = var.command
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_alias.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_alias.this.name
}

output "this" {
  value = fortios_system_alias.this
}
```

[top](#index)