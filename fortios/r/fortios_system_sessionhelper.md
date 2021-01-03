# fortios_system_sessionhelper

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
module "fortios_system_sessionhelper" {
  source = "./modules/fortios/r/fortios_system_sessionhelper"

  # fosid - (optional) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null
  # port - (required) is a type of number
  port = null
  # protocol - (required) is a type of number
  protocol = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_sessionhelper" "this" {
  fosid    = var.fosid
  name     = var.name
  port     = var.port
  protocol = var.protocol
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_system_sessionhelper.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_system_sessionhelper.this.id
}

output "this" {
  value = fortios_system_sessionhelper.this
}
```

[top](#index)