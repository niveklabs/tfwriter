# cloudscale_network

[back](../cloudscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudscale = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudscale_network" {
  source = "./modules/cloudscale/r/cloudscale_network"

  # auto_create_ipv4_subnet - (optional) is a type of bool
  auto_create_ipv4_subnet = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # zone_slug - (optional) is a type of string
  zone_slug = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_create_ipv4_subnet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "zone_slug" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudscale_network" "this" {
  # auto_create_ipv4_subnet - (optional) is a type of bool
  auto_create_ipv4_subnet = var.auto_create_ipv4_subnet
  # mtu - (optional) is a type of number
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # zone_slug - (optional) is a type of string
  zone_slug = var.zone_slug
}
```

[top](#index)

### Outputs

```terraform
output "href" {
  description = "returns a string"
  value       = cloudscale_network.this.href
}

output "id" {
  description = "returns a string"
  value       = cloudscale_network.this.id
}

output "mtu" {
  description = "returns a number"
  value       = cloudscale_network.this.mtu
}

output "subnets" {
  description = "returns a list of object"
  value       = cloudscale_network.this.subnets
}

output "zone_slug" {
  description = "returns a string"
  value       = cloudscale_network.this.zone_slug
}

output "this" {
  value = cloudscale_network.this
}
```

[top](#index)