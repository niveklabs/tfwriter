# fortios_router_authpath

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
module "fortios_router_authpath" {
  source = "./modules/fortios/r/fortios_router_authpath"

  # device - (required) is a type of string
  device = null
  # gateway - (optional) is a type of string
  gateway = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "device" {
  description = "(required)"
  type        = string
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_authpath" "this" {
  device  = var.device
  gateway = var.gateway
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "gateway" {
  description = "returns a string"
  value       = fortios_router_authpath.this.gateway
}

output "id" {
  description = "returns a string"
  value       = fortios_router_authpath.this.id
}

output "this" {
  value = fortios_router_authpath.this
}
```

[top](#index)