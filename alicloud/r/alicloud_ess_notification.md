# alicloud_ess_notification

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
module "alicloud_ess_notification" {
  source = "./modules/alicloud/r/alicloud_ess_notification"

  # notification_arn - (required) is a type of string
  notification_arn = null
  # notification_types - (required) is a type of set of string
  notification_types = []
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "notification_arn" {
  description = "(required)"
  type        = string
}

variable "notification_types" {
  description = "(required)"
  type        = set(string)
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_notification" "this" {
  notification_arn   = var.notification_arn
  notification_types = var.notification_types
  scaling_group_id   = var.scaling_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ess_notification.this.id
}

output "this" {
  value = alicloud_ess_notification.this
}
```

[top](#index)