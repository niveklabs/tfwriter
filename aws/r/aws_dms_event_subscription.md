# aws_dms_event_subscription

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_dms_event_subscription" {
  source = "./modules/aws/r/aws_dms_event_subscription"

  # enabled - (optional) is a type of bool
  enabled = null
  # event_categories - (required) is a type of set of string
  event_categories = []
  # name - (required) is a type of string
  name = null
  # sns_topic_arn - (required) is a type of string
  sns_topic_arn = null
  # source_ids - (optional) is a type of set of string
  source_ids = []
  # source_type - (optional) is a type of string
  source_type = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "event_categories" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "sns_topic_arn" {
  description = "(required)"
  type        = string
}

variable "source_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_type" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_dms_event_subscription" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # event_categories - (required) is a type of set of string
  event_categories = var.event_categories
  # name - (required) is a type of string
  name = var.name
  # sns_topic_arn - (required) is a type of string
  sns_topic_arn = var.sns_topic_arn
  # source_ids - (optional) is a type of set of string
  source_ids = var.source_ids
  # source_type - (optional) is a type of string
  source_type = var.source_type
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_dms_event_subscription.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_dms_event_subscription.this.id
}

output "this" {
  value = aws_dms_event_subscription.this
}
```

[top](#index)