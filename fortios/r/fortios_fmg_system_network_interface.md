# fortios_fmg_system_network_interface

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
module "fortios_fmg_system_network_interface" {
  source = "./modules/fortios/r/fortios_fmg_system_network_interface"

  # allow_access - (optional) is a type of list of string
  allow_access = []
  # description - (optional) is a type of string
  description = null
  # ip - (optional) is a type of string
  ip = null
  # name - (required) is a type of string
  name = null
  # service_access - (optional) is a type of list of string
  service_access = []
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_access" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "service_access" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_network_interface" "this" {
  allow_access   = var.allow_access
  description    = var.description
  ip             = var.ip
  name           = var.name
  service_access = var.service_access
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_network_interface.this.id
}

output "this" {
  value = fortios_fmg_system_network_interface.this
}
```

[top](#index)