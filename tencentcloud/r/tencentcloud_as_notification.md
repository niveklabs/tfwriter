# tencentcloud_as_notification

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
module "tencentcloud_as_notification" {
  source = "./modules/tencentcloud/r/tencentcloud_as_notification"

  # notification_types - (required) is a type of list of string
  notification_types = []
  # notification_user_group_ids - (required) is a type of list of string
  notification_user_group_ids = []
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "notification_types" {
  description = "(required) - A list of Notification Types that trigger notifications. Acceptable values are `SCALE_OUT_FAILED`, `SCALE_IN_SUCCESSFUL`, `SCALE_IN_FAILED`, `REPLACE_UNHEALTHY_INSTANCE_SUCCESSFUL` and `REPLACE_UNHEALTHY_INSTANCE_FAILED`."
  type        = list(string)
}

variable "notification_user_group_ids" {
  description = "(required) - A group of user IDs to be notified."
  type        = list(string)
}

variable "scaling_group_id" {
  description = "(required) - ID of a scaling group."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_as_notification" "this" {
  # notification_types - (required) is a type of list of string
  notification_types = var.notification_types
  # notification_user_group_ids - (required) is a type of list of string
  notification_user_group_ids = var.notification_user_group_ids
  # scaling_group_id - (required) is a type of string
  scaling_group_id = var.scaling_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_as_notification.this.id
}

output "this" {
  value = tencentcloud_as_notification.this
}
```

[top](#index)