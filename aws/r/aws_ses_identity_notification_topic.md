# aws_ses_identity_notification_topic

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
module "aws_ses_identity_notification_topic" {
  source = "./modules/aws/r/aws_ses_identity_notification_topic"

  # identity - (required) is a type of string
  identity = null
  # include_original_headers - (optional) is a type of bool
  include_original_headers = null
  # notification_type - (required) is a type of string
  notification_type = null
  # topic_arn - (optional) is a type of string
  topic_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "identity" {
  description = "(required)"
  type        = string
}

variable "include_original_headers" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "notification_type" {
  description = "(required)"
  type        = string
}

variable "topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_ses_identity_notification_topic" "this" {
  identity                 = var.identity
  include_original_headers = var.include_original_headers
  notification_type        = var.notification_type
  topic_arn                = var.topic_arn
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ses_identity_notification_topic.this.id
}

output "this" {
  value = aws_ses_identity_notification_topic.this
}
```

[top](#index)