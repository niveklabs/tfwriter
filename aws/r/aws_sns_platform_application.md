# aws_sns_platform_application

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_sns_platform_application" {
  source = "./modules/aws/r/aws_sns_platform_application"

  # event_delivery_failure_topic_arn - (optional) is a type of string
  event_delivery_failure_topic_arn = null
  # event_endpoint_created_topic_arn - (optional) is a type of string
  event_endpoint_created_topic_arn = null
  # event_endpoint_deleted_topic_arn - (optional) is a type of string
  event_endpoint_deleted_topic_arn = null
  # event_endpoint_updated_topic_arn - (optional) is a type of string
  event_endpoint_updated_topic_arn = null
  # failure_feedback_role_arn - (optional) is a type of string
  failure_feedback_role_arn = null
  # name - (required) is a type of string
  name = null
  # platform - (required) is a type of string
  platform = null
  # platform_credential - (required) is a type of string
  platform_credential = null
  # platform_principal - (optional) is a type of string
  platform_principal = null
  # success_feedback_role_arn - (optional) is a type of string
  success_feedback_role_arn = null
  # success_feedback_sample_rate - (optional) is a type of string
  success_feedback_sample_rate = null
}
```

[top](#index)

### Variables

```hcl
variable "event_delivery_failure_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event_endpoint_created_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event_endpoint_deleted_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event_endpoint_updated_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "failure_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "platform" {
  description = "(required)"
  type        = string
}

variable "platform_credential" {
  description = "(required)"
  type        = string
}

variable "platform_principal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "success_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "success_feedback_sample_rate" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_sns_platform_application" "this" {
  event_delivery_failure_topic_arn = var.event_delivery_failure_topic_arn
  event_endpoint_created_topic_arn = var.event_endpoint_created_topic_arn
  event_endpoint_deleted_topic_arn = var.event_endpoint_deleted_topic_arn
  event_endpoint_updated_topic_arn = var.event_endpoint_updated_topic_arn
  failure_feedback_role_arn        = var.failure_feedback_role_arn
  name                             = var.name
  platform                         = var.platform
  platform_credential              = var.platform_credential
  platform_principal               = var.platform_principal
  success_feedback_role_arn        = var.success_feedback_role_arn
  success_feedback_sample_rate     = var.success_feedback_sample_rate
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_sns_platform_application.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sns_platform_application.this.id
}

output "this" {
  value = aws_sns_platform_application.this
}
```

[top](#index)