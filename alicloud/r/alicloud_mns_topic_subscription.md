# alicloud_mns_topic_subscription

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
module "alicloud_mns_topic_subscription" {
  source = "./modules/alicloud/r/alicloud_mns_topic_subscription"

  # endpoint - (required) is a type of string
  endpoint = null
  # filter_tag - (optional) is a type of string
  filter_tag = null
  # name - (required) is a type of string
  name = null
  # notify_content_format - (optional) is a type of string
  notify_content_format = null
  # notify_strategy - (optional) is a type of string
  notify_strategy = null
  # topic_name - (required) is a type of string
  topic_name = null
}
```

[top](#index)

### Variables

```terraform
variable "endpoint" {
  description = "(required)"
  type        = string
}

variable "filter_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notify_content_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notify_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "topic_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_mns_topic_subscription" "this" {
  # endpoint - (required) is a type of string
  endpoint = var.endpoint
  # filter_tag - (optional) is a type of string
  filter_tag = var.filter_tag
  # name - (required) is a type of string
  name = var.name
  # notify_content_format - (optional) is a type of string
  notify_content_format = var.notify_content_format
  # notify_strategy - (optional) is a type of string
  notify_strategy = var.notify_strategy
  # topic_name - (required) is a type of string
  topic_name = var.topic_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_mns_topic_subscription.this.id
}

output "this" {
  value = alicloud_mns_topic_subscription.this
}
```

[top](#index)