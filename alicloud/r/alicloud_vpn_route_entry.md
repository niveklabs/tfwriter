# alicloud_vpn_route_entry

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_vpn_route_entry" {
  source = "./modules/alicloud/r/alicloud_vpn_route_entry"

  # next_hop - (required) is a type of string
  next_hop = null
  # publish_vpc - (required) is a type of bool
  publish_vpc = null
  # route_dest - (required) is a type of string
  route_dest = null
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = null
  # weight - (required) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "next_hop" {
  description = "(required)"
  type        = string
}

variable "publish_vpc" {
  description = "(required)"
  type        = bool
}

variable "route_dest" {
  description = "(required)"
  type        = string
}

variable "vpn_gateway_id" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_vpn_route_entry" "this" {
  next_hop       = var.next_hop
  publish_vpc    = var.publish_vpc
  route_dest     = var.route_dest
  vpn_gateway_id = var.vpn_gateway_id
  weight         = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_vpn_route_entry.this.id
}

output "this" {
  value = alicloud_vpn_route_entry.this
}
```

[top](#index)