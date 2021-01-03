# alicloud_ess_notifications

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_ess_notifications" {
  source = "./modules/alicloud/d/alicloud_ess_notifications"

  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ess_notifications" "this" {
  ids              = var.ids
  output_file      = var.output_file
  scaling_group_id = var.scaling_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ess_notifications.this.id
}

output "notifications" {
  description = "returns a list of object"
  value       = data.alicloud_ess_notifications.this.notifications
}

output "this" {
  value = alicloud_ess_notifications.this
}
```

[top](#index)