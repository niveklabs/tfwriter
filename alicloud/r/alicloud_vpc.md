# alicloud_vpc

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
module "alicloud_vpc" {
  source = "./modules/alicloud/r/alicloud_vpc"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(required)"
  type        = string
}

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

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_vpc" "this" {
  cidr_block        = var.cidr_block
  description       = var.description
  name              = var.name
  resource_group_id = var.resource_group_id
  tags              = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_vpc.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_vpc.this.resource_group_id
}

output "route_table_id" {
  description = "returns a string"
  value       = alicloud_vpc.this.route_table_id
}

output "router_id" {
  description = "returns a string"
  value       = alicloud_vpc.this.router_id
}

output "router_table_id" {
  description = "returns a string"
  value       = alicloud_vpc.this.router_table_id
}

output "this" {
  value = alicloud_vpc.this
}
```

[top](#index)