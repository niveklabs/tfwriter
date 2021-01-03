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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_snapshot_policy" {
  source = "./modules/alicloud/r/alicloud_snapshot_policy"

  # name - (optional) is a type of string
  name = null
  # repeat_weekdays - (required) is a type of set of string
  repeat_weekdays = []
  # retention_days - (required) is a type of number
  retention_days = null
  # time_points - (required) is a type of set of string
  time_points = []
}
```

[top](#index)

### Variables

```terraform
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

variable "time_points" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_snapshot_policy" "this" {
  name            = var.name
  repeat_weekdays = var.repeat_weekdays
  retention_days  = var.retention_days
  time_points     = var.time_points
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_snapshot_policy.this.id
}

output "this" {
  value = alicloud_snapshot_policy.this
}
```

[top](#index)