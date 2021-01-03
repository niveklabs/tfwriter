# alicloud_datahub_subscription

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
module "alicloud_datahub_subscription" {
  source = "./modules/alicloud/r/alicloud_datahub_subscription"

  # comment - (optional) is a type of string
  comment = null
  # project_name - (required) is a type of string
  project_name = null
  # topic_name - (required) is a type of string
  topic_name = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_name" {
  description = "(required)"
  type        = string
}

variable "topic_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_datahub_subscription" "this" {
  comment      = var.comment
  project_name = var.project_name
  topic_name   = var.topic_name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = alicloud_datahub_subscription.this.create_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_datahub_subscription.this.id
}

output "last_modify_time" {
  description = "returns a string"
  value       = alicloud_datahub_subscription.this.last_modify_time
}

output "sub_id" {
  description = "returns a string"
  value       = alicloud_datahub_subscription.this.sub_id
}

output "this" {
  value = alicloud_datahub_subscription.this
}
```

[top](#index)