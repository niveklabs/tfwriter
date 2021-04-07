# tencentcloud_route_entry

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_route_entry" {
  source = "./modules/tencentcloud/r/tencentcloud_route_entry"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # next_hub - (required) is a type of string
  next_hub = null
  # next_type - (required) is a type of string
  next_type = null
  # route_table_id - (required) is a type of string
  route_table_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(required) - The RouteEntry's target network segment."
  type        = string
}

variable "next_hub" {
  description = "(required) - The route entry's next hub. CVM instance ID or VPC router interface ID."
  type        = string
}

variable "next_type" {
  description = "(required) - The next hop type. Valid values: `public_gateway`,`vpn_gateway`,`sslvpn_gateway`,`dc_gateway`,`peering_connection`,`nat_gateway` and `instance`. `instance` points to CVM Instance."
  type        = string
}

variable "route_table_id" {
  description = "(required) - The ID of the route table."
  type        = string
}

variable "vpc_id" {
  description = "(required) - The VPC ID."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_route_entry" "this" {
  cidr_block     = var.cidr_block
  next_hub       = var.next_hub
  next_type      = var.next_type
  route_table_id = var.route_table_id
  vpc_id         = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_route_entry.this.id
}

output "this" {
  value = tencentcloud_route_entry.this
}
```

[top](#index)