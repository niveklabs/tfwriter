# fortios_system_console

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
module "fortios_system_console" {
  source = "./modules/fortios/r/fortios_system_console"

  # baudrate - (optional) is a type of string
  baudrate = null
  # login - (optional) is a type of string
  login = null
  # mode - (optional) is a type of string
  mode = null
  # output - (optional) is a type of string
  output = null
}
```

[top](#index)

### Variables

```terraform
variable "baudrate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_console" "this" {
  baudrate = var.baudrate
  login    = var.login
  mode     = var.mode
  output   = var.output
}
```

[top](#index)

### Outputs

```terraform
output "baudrate" {
  description = "returns a string"
  value       = fortios_system_console.this.baudrate
}

output "id" {
  description = "returns a string"
  value       = fortios_system_console.this.id
}

output "login" {
  description = "returns a string"
  value       = fortios_system_console.this.login
}

output "mode" {
  description = "returns a string"
  value       = fortios_system_console.this.mode
}

output "output" {
  description = "returns a string"
  value       = fortios_system_console.this.output
}

output "this" {
  value = fortios_system_console.this
}
```

[top](#index)