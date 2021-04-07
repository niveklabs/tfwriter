# alicloud_cen_route_entry

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
module "alicloud_cen_route_entry" {
  source = "./modules/alicloud/r/alicloud_cen_route_entry"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # instance_id - (required) is a type of string
  instance_id = null
  # route_table_id - (required) is a type of string
  route_table_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "route_table_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cen_route_entry" "this" {
  # cidr_block - (required) is a type of string
  cidr_block = var.cidr_block
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # route_table_id - (required) is a type of string
  route_table_id = var.route_table_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cen_route_entry.this.id
}

output "this" {
  value = alicloud_cen_route_entry.this
}
```

[top](#index)