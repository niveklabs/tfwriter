# tencentcloud_cbs_snapshot_policy

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_cbs_snapshot_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_cbs_snapshot_policy"

  # repeat_hours - (required) is a type of list of number
  repeat_hours = []
  # repeat_weekdays - (required) is a type of list of number
  repeat_weekdays = []
  # retention_days - (optional) is a type of number
  retention_days = null
  # snapshot_policy_name - (required) is a type of string
  snapshot_policy_name = null
}
```

[top](#index)

### Variables

```terraform
variable "repeat_hours" {
  description = "(required) - Trigger times of periodic snapshot. Valid value ranges: (0~23). The 0 means 00:00, and so on."
  type        = list(number)
}

variable "repeat_weekdays" {
  description = "(required) - Periodic snapshot is enabled. Valid values: [0, 1, 2, 3, 4, 5, 6]. 0 means Sunday, 1-6 means Monday to Saturday."
  type        = list(number)
}

variable "retention_days" {
  description = "(optional) - Retention days of the snapshot, and the default value is 7."
  type        = number
  default     = null
}

variable "snapshot_policy_name" {
  description = "(required) - Name of snapshot policy. The maximum length can not exceed 60 bytes."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cbs_snapshot_policy" "this" {
  # repeat_hours - (required) is a type of list of number
  repeat_hours = var.repeat_hours
  # repeat_weekdays - (required) is a type of list of number
  repeat_weekdays = var.repeat_weekdays
  # retention_days - (optional) is a type of number
  retention_days = var.retention_days
  # snapshot_policy_name - (required) is a type of string
  snapshot_policy_name = var.snapshot_policy_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_cbs_snapshot_policy.this.id
}

output "this" {
  value = tencentcloud_cbs_snapshot_policy.this
}
```

[top](#index)