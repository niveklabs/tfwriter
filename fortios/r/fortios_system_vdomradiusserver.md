# fortios_system_vdomradiusserver

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
module "fortios_system_vdomradiusserver" {
  source = "./modules/fortios/r/fortios_system_vdomradiusserver"

  # name - (optional) is a type of string
  name = null
  # radius_server_vdom - (required) is a type of string
  radius_server_vdom = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_server_vdom" {
  description = "(required)"
  type        = string
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
resource "fortios_system_vdomradiusserver" "this" {
  name               = var.name
  radius_server_vdom = var.radius_server_vdom
  status             = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_vdomradiusserver.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_vdomradiusserver.this.name
}

output "status" {
  description = "returns a string"
  value       = fortios_system_vdomradiusserver.this.status
}

output "this" {
  value = fortios_system_vdomradiusserver.this
}
```

[top](#index)