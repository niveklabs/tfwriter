# alicloud_ecs_snapshot

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
module "alicloud_ecs_snapshot" {
  source = "./modules/alicloud/r/alicloud_ecs_snapshot"

  # category - (optional) is a type of string
  category = null
  # description - (optional) is a type of string
  description = null
  # disk_id - (required) is a type of string
  disk_id = null
  # force - (optional) is a type of bool
  force = null
  # instant_access - (optional) is a type of bool
  instant_access = null
  # instant_access_retention_days - (optional) is a type of number
  instant_access_retention_days = null
  # name - (optional) is a type of string
  name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # retention_days - (optional) is a type of number
  retention_days = null
  # snapshot_name - (optional) is a type of string
  snapshot_name = null
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
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_id" {
  description = "(required)"
  type        = string
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instant_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instant_access_retention_days" {
  description = "(optional)"
  type        = number
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

variable "retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snapshot_name" {
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
resource "alicloud_ecs_snapshot" "this" {
  # category - (optional) is a type of string
  category = var.category
  # description - (optional) is a type of string
  description = var.description
  # disk_id - (required) is a type of string
  disk_id = var.disk_id
  # force - (optional) is a type of bool
  force = var.force
  # instant_access - (optional) is a type of bool
  instant_access = var.instant_access
  # instant_access_retention_days - (optional) is a type of number
  instant_access_retention_days = var.instant_access_retention_days
  # name - (optional) is a type of string
  name = var.name
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # retention_days - (optional) is a type of number
  retention_days = var.retention_days
  # snapshot_name - (optional) is a type of string
  snapshot_name = var.snapshot_name
  # tags - (optional) is a type of map of string
  tags = var.tags

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
  value       = alicloud_ecs_snapshot.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_ecs_snapshot.this.name
}

output "snapshot_name" {
  description = "returns a string"
  value       = alicloud_ecs_snapshot.this.snapshot_name
}

output "status" {
  description = "returns a string"
  value       = alicloud_ecs_snapshot.this.status
}

output "this" {
  value = alicloud_ecs_snapshot.this
}
```

[top](#index)