# fortios_fmg_system_syslogserver

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
module "fortios_fmg_system_syslogserver" {
  source = "./modules/fortios/r/fortios_fmg_system_syslogserver"

  # ip - (optional) is a type of string
  ip = null
  # name - (required) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_syslogserver" "this" {
  # ip - (optional) is a type of string
  ip = var.ip
  # name - (required) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_syslogserver.this.id
}

output "this" {
  value = fortios_fmg_system_syslogserver.this
}
```

[top](#index)