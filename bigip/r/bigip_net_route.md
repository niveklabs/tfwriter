# bigip_net_route

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_net_route" {
  source = "./modules/bigip/r/bigip_net_route"

  # gw - (optional) is a type of string
  gw = null
  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
}
```

[top](#index)

### Variables

```terraform
variable "gw" {
  description = "(optional) - Gateway address"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the route"
  type        = string
}

variable "network" {
  description = "(required) - Destination network"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_net_route" "this" {
  # gw - (optional) is a type of string
  gw = var.gw
  # name - (required) is a type of string
  name = var.name
  # network - (required) is a type of string
  network = var.network
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_net_route.this.id
}

output "this" {
  value = bigip_net_route.this
}
```

[top](#index)