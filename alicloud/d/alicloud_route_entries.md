# alicloud_route_entries

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_route_entries" {
  source = "./modules/alicloud/d/alicloud_route_entries"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # route_table_id - (required) is a type of string
  route_table_id = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_route_entries" "this" {
  cidr_block     = var.cidr_block
  instance_id    = var.instance_id
  output_file    = var.output_file
  route_table_id = var.route_table_id
  type           = var.type
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.alicloud_route_entries.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_route_entries.this.id
}

output "this" {
  value = alicloud_route_entries.this
}
```

[top](#index)