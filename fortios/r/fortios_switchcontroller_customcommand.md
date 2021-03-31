# fortios_switchcontroller_customcommand

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_customcommand" {
  source = "./modules/fortios/r/fortios_switchcontroller_customcommand"

  # command - (required) is a type of string
  command = null
  # command_name - (optional) is a type of string
  command_name = null
  # description - (optional) is a type of string
  description = null
}
```

[top](#index)

### Variables

```terraform
variable "command" {
  description = "(required)"
  type        = string
}

variable "command_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_customcommand" "this" {
  command      = var.command
  command_name = var.command_name
  description  = var.description
}
```

[top](#index)

### Outputs

```terraform
output "command_name" {
  description = "returns a string"
  value       = fortios_switchcontroller_customcommand.this.command_name
}

output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_customcommand.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_customcommand.this.id
}

output "this" {
  value = fortios_switchcontroller_customcommand.this
}
```

[top](#index)