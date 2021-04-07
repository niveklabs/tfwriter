# aws_sns_topic_subscription

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
module "aws_sns_topic_subscription" {
  source = "./modules/aws/r/aws_sns_topic_subscription"

  # confirmation_timeout_in_minutes - (optional) is a type of number
  confirmation_timeout_in_minutes = null
  # delivery_policy - (optional) is a type of string
  delivery_policy = null
  # endpoint - (required) is a type of string
  endpoint = null
  # endpoint_auto_confirms - (optional) is a type of bool
  endpoint_auto_confirms = null
  # filter_policy - (optional) is a type of string
  filter_policy = null
  # protocol - (required) is a type of string
  protocol = null
  # raw_message_delivery - (optional) is a type of bool
  raw_message_delivery = null
  # redrive_policy - (optional) is a type of string
  redrive_policy = null
  # subscription_role_arn - (optional) is a type of string
  subscription_role_arn = null
  # topic_arn - (required) is a type of string
  topic_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "confirmation_timeout_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "delivery_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint" {
  description = "(required)"
  type        = string
}

variable "endpoint_auto_confirms" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "filter_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "raw_message_delivery" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "redrive_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "topic_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_sns_topic_subscription" "this" {
  # confirmation_timeout_in_minutes - (optional) is a type of number
  confirmation_timeout_in_minutes = var.confirmation_timeout_in_minutes
  # delivery_policy - (optional) is a type of string
  delivery_policy = var.delivery_policy
  # endpoint - (required) is a type of string
  endpoint = var.endpoint
  # endpoint_auto_confirms - (optional) is a type of bool
  endpoint_auto_confirms = var.endpoint_auto_confirms
  # filter_policy - (optional) is a type of string
  filter_policy = var.filter_policy
  # protocol - (required) is a type of string
  protocol = var.protocol
  # raw_message_delivery - (optional) is a type of bool
  raw_message_delivery = var.raw_message_delivery
  # redrive_policy - (optional) is a type of string
  redrive_policy = var.redrive_policy
  # subscription_role_arn - (optional) is a type of string
  subscription_role_arn = var.subscription_role_arn
  # topic_arn - (required) is a type of string
  topic_arn = var.topic_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sns_topic_subscription.this.arn
}

output "confirmation_was_authenticated" {
  description = "returns a bool"
  value       = aws_sns_topic_subscription.this.confirmation_was_authenticated
}

output "id" {
  description = "returns a string"
  value       = aws_sns_topic_subscription.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_sns_topic_subscription.this.owner_id
}

output "pending_confirmation" {
  description = "returns a bool"
  value       = aws_sns_topic_subscription.this.pending_confirmation
}

output "this" {
  value = aws_sns_topic_subscription.this
}
```

[top](#index)