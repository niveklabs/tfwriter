# fortios_fmg_system_network_route

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
module "fortios_fmg_system_network_route" {
  source = "./modules/fortios/r/fortios_fmg_system_network_route"

  # destination - (required) is a type of string
  destination = null
  # device - (required) is a type of string
  device = null
  # gateway - (required) is a type of string
  gateway = null
  # route_id - (required) is a type of number
  route_id = null
}
```

[top](#index)

### Variables

```terraform
variable "destination" {
  description = "(required)"
  type        = string
}

variable "device" {
  description = "(required)"
  type        = string
}

variable "gateway" {
  description = "(required)"
  type        = string
}

variable "route_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_network_route" "this" {
  destination = var.destination
  device      = var.device
  gateway     = var.gateway
  route_id    = var.route_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_network_route.this.id
}

output "this" {
  value = fortios_fmg_system_network_route.this
}
```

[top](#index)