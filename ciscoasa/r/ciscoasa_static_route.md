# ciscoasa_static_route

[back](../ciscoasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ciscoasa = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ciscoasa_static_route" {
  source = "./modules/ciscoasa/r/ciscoasa_static_route"

  # gateway - (required) is a type of string
  gateway = null
  # interface - (required) is a type of string
  interface = null
  # metric - (optional) is a type of number
  metric = null
  # network - (required) is a type of string
  network = null
  # tracked - (optional) is a type of bool
  tracked = null
  # tunneled - (optional) is a type of bool
  tunneled = null
}
```

[top](#index)

### Variables

```terraform
variable "gateway" {
  description = "(required)"
  type        = string
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "metric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "network" {
  description = "(required)"
  type        = string
}

variable "tracked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tunneled" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ciscoasa_static_route" "this" {
  gateway   = var.gateway
  interface = var.interface
  metric    = var.metric
  network   = var.network
  tracked   = var.tracked
  tunneled  = var.tunneled
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ciscoasa_static_route.this.id
}

output "this" {
  value = ciscoasa_static_route.this
}
```

[top](#index)