# alicloud_route_table

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
module "alicloud_route_table" {
  source = "./modules/alicloud/r/alicloud_route_table"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # route_table_name - (optional) is a type of string
  route_table_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_route_table" "this" {
  description      = var.description
  name             = var.name
  route_table_name = var.route_table_name
  tags             = var.tags
  vpc_id           = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_route_table.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_route_table.this.name
}

output "route_table_name" {
  description = "returns a string"
  value       = alicloud_route_table.this.route_table_name
}

output "status" {
  description = "returns a string"
  value       = alicloud_route_table.this.status
}

output "this" {
  value = alicloud_route_table.this
}
```

[top](#index)