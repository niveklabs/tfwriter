# aws_pinpoint_sms_channel

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
module "aws_pinpoint_sms_channel" {
  source = "./modules/aws/r/aws_pinpoint_sms_channel"

  # application_id - (required) is a type of string
  application_id = null
  # enabled - (optional) is a type of bool
  enabled = null
  # sender_id - (optional) is a type of string
  sender_id = null
  # short_code - (optional) is a type of string
  short_code = null
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sender_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "short_code" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_pinpoint_sms_channel" "this" {
  # application_id - (required) is a type of string
  application_id = var.application_id
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # sender_id - (optional) is a type of string
  sender_id = var.sender_id
  # short_code - (optional) is a type of string
  short_code = var.short_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_pinpoint_sms_channel.this.id
}

output "promotional_messages_per_second" {
  description = "returns a number"
  value       = aws_pinpoint_sms_channel.this.promotional_messages_per_second
}

output "transactional_messages_per_second" {
  description = "returns a number"
  value       = aws_pinpoint_sms_channel.this.transactional_messages_per_second
}

output "this" {
  value = aws_pinpoint_sms_channel.this
}
```

[top](#index)