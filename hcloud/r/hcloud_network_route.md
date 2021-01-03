# hcloud_network_route

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_network_route" {
  source = "./modules/hcloud/r/hcloud_network_route"

  # destination - (required) is a type of string
  destination = null
  # gateway - (required) is a type of string
  gateway = null
  # network_id - (required) is a type of number
  network_id = null
}
```

[top](#index)

### Variables

```terraform
variable "destination" {
  description = "(required)"
  type        = string
}

variable "gateway" {
  description = "(required)"
  type        = string
}

variable "network_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_network_route" "this" {
  destination = var.destination
  gateway     = var.gateway
  network_id  = var.network_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_network_route.this.id
}

output "this" {
  value = hcloud_network_route.this
}
```

[top](#index)