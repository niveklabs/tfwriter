# alicloud_snapshot_policy

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_snapshot_policy" {
  source = "./modules/alicloud/r/alicloud_snapshot_policy"

  # copied_snapshots_retention_days - (optional) is a type of number
  copied_snapshots_retention_days = null
  # enable_cross_region_copy - (optional) is a type of bool
  enable_cross_region_copy = null
  # name - (optional) is a type of string
  name = null
  # repeat_weekdays - (required) is a type of set of string
  repeat_weekdays = []
  # retention_days - (required) is a type of number
  retention_days = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_copy_regions - (optional) is a type of set of string
  target_copy_regions = []
  # time_points - (required) is a type of set of string
  time_points = []

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "copied_snapshots_retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_cross_region_copy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repeat_weekdays" {
  description = "(required)"
  type        = set(string)
}

variable "retention_days" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_copy_regions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "time_points" {
  description = "(required)"
  type        = set(string)
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
resource "alicloud_snapshot_policy" "this" {
  copied_snapshots_retention_days = var.copied_snapshots_retention_days
  enable_cross_region_copy        = var.enable_cross_region_copy
  name                            = var.name
  repeat_weekdays                 = var.repeat_weekdays
  retention_days                  = var.retention_days
  tags                            = var.tags
  target_copy_regions             = var.target_copy_regions
  time_points                     = var.time_points

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
  value       = alicloud_snapshot_policy.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_snapshot_policy.this.status
}

output "this" {
  value = alicloud_snapshot_policy.this
}
```

[top](#index)