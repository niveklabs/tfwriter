# alicloud_resource_manager_resource_group

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
module "alicloud_resource_manager_resource_group" {
  source = "./modules/alicloud/r/alicloud_resource_manager_resource_group"

  # display_name - (required) is a type of string
  display_name = null
  # name - (optional) is a type of string
  name = null
  # resource_group_name - (optional) is a type of string
  resource_group_name = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "alicloud_resource_manager_resource_group" "this" {
  display_name        = var.display_name
  name                = var.name
  resource_group_name = var.resource_group_name

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
output "account_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_group.this.account_id
}

output "create_date" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_group.this.create_date
}

output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_group.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_group.this.name
}

output "region_statuses" {
  description = "returns a list of object"
  value       = alicloud_resource_manager_resource_group.this.region_statuses
}

output "resource_group_name" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_group.this.resource_group_name
}

output "status" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_group.this.status
}

output "this" {
  value = alicloud_resource_manager_resource_group.this
}
```

[top](#index)