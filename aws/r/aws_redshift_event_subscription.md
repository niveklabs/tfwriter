# aws_redshift_event_subscription

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_redshift_event_subscription" {
  source = "./modules/aws/r/aws_redshift_event_subscription"

  # enabled - (optional) is a type of bool
  enabled = null
  # event_categories - (optional) is a type of set of string
  event_categories = []
  # name - (required) is a type of string
  name = null
  # severity - (optional) is a type of string
  severity = null
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
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "aws_redshift_event_subscription" "this" {
  enabled          = var.enabled
  event_categories = var.event_categories
  name             = var.name
  severity         = var.severity
  sns_topic_arn    = var.sns_topic_arn
  source_ids       = var.source_ids
  source_type      = var.source_type
  tags             = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = aws_redshift_event_subscription.this.arn
}

output "customer_aws_id" {
  description = "returns a string"
  value       = aws_redshift_event_subscription.this.customer_aws_id
}

output "id" {
  description = "returns a string"
  value       = aws_redshift_event_subscription.this.id
}

output "status" {
  description = "returns a string"
  value       = aws_redshift_event_subscription.this.status
}

output "this" {
  value = aws_redshift_event_subscription.this
}
```

[top](#index)