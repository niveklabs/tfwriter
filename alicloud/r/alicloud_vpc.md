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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_vpc" {
  source = "./modules/alicloud/r/alicloud_vpc"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # description - (optional) is a type of string
  description = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = null
  # name - (optional) is a type of string
  name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # secondary_cidr_blocks - (optional) is a type of list of string
  secondary_cidr_blocks = []
  # tags - (optional) is a type of map of string
  tags = {}
  # user_cidrs - (optional) is a type of list of string
  user_cidrs = []
  # vpc_name - (optional) is a type of string
  vpc_name = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ipv6" {
  description = "(optional)"
  type        = bool
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

variable "secondary_cidr_blocks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_cidrs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "vpc_name" {
  description = "(optional)"
  type        = string
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
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # description - (optional) is a type of string
  description = var.description
  # dry_run - (optional) is a type of bool
  dry_run = var.dry_run
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = var.enable_ipv6
  # name - (optional) is a type of string
  name = var.name
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # secondary_cidr_blocks - (optional) is a type of list of string
  secondary_cidr_blocks = var.secondary_cidr_blocks
  # tags - (optional) is a type of map of string
  tags = var.tags
  # user_cidrs - (optional) is a type of list of string
  user_cidrs = var.user_cidrs
  # vpc_name - (optional) is a type of string
  vpc_name = var.vpc_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
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

output "ipv6_cidr_block" {
  description = "returns a string"
  value       = alicloud_vpc.this.ipv6_cidr_block
}

output "name" {
  description = "returns a string"
  value       = alicloud_vpc.this.name
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

output "status" {
  description = "returns a string"
  value       = alicloud_vpc.this.status
}

output "vpc_name" {
  description = "returns a string"
  value       = alicloud_vpc.this.vpc_name
}

output "this" {
  value = alicloud_vpc.this
}
```

[top](#index)