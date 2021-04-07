# tencentcloud_vpc_route_tables

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_vpc_route_tables" {
  source = "./modules/tencentcloud/d/tencentcloud_vpc_route_tables"

  # association_main - (optional) is a type of bool
  association_main = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # tag_key - (optional) is a type of string
  tag_key = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "association_main" {
  description = "(optional) - Filter the main routing table."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Name of the routing table to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(optional) - ID of the routing table to be queried."
  type        = string
  default     = null
}

variable "tag_key" {
  description = "(optional) - Filter if routing table has this tag."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the routing table to be queried."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_vpc_route_tables" "this" {
  association_main   = var.association_main
  name               = var.name
  result_output_file = var.result_output_file
  route_table_id     = var.route_table_id
  tag_key            = var.tag_key
  tags               = var.tags
  vpc_id             = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_vpc_route_tables.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_vpc_route_tables.this.instance_list
}

output "this" {
  value = tencentcloud_vpc_route_tables.this
}
```

[top](#index)