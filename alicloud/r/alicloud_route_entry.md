# alicloud_route_entry

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_route_entry" {
  source = "./modules/alicloud/r/alicloud_route_entry"

  # destination_cidrblock - (optional) is a type of string
  destination_cidrblock = null
  # name - (optional) is a type of string
  name = null
  # nexthop_id - (optional) is a type of string
  nexthop_id = null
  # nexthop_type - (optional) is a type of string
  nexthop_type = null
  # route_table_id - (required) is a type of string
  route_table_id = null
  # router_id - (optional) is a type of string
  router_id = null
}
```

[top](#index)

### Variables

```terraform
variable "destination_cidrblock" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nexthop_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nexthop_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "router_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_route_entry" "this" {
  destination_cidrblock = var.destination_cidrblock
  name                  = var.name
  nexthop_id            = var.nexthop_id
  nexthop_type          = var.nexthop_type
  route_table_id        = var.route_table_id
  router_id             = var.router_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_route_entry.this.id
}

output "router_id" {
  description = "returns a string"
  value       = alicloud_route_entry.this.router_id
}

output "this" {
  value = alicloud_route_entry.this
}
```

[top](#index)