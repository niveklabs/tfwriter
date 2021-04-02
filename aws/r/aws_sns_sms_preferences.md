# aws_sns_sms_preferences

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
module "aws_sns_sms_preferences" {
  source = "./modules/aws/r/aws_sns_sms_preferences"

  # default_sender_id - (optional) is a type of string
  default_sender_id = null
  # default_sms_type - (optional) is a type of string
  default_sms_type = null
  # delivery_status_iam_role_arn - (optional) is a type of string
  delivery_status_iam_role_arn = null
  # delivery_status_success_sampling_rate - (optional) is a type of string
  delivery_status_success_sampling_rate = null
  # monthly_spend_limit - (optional) is a type of string
  monthly_spend_limit = null
  # usage_report_s3_bucket - (optional) is a type of string
  usage_report_s3_bucket = null
}
```

[top](#index)

### Variables

```terraform
variable "default_sender_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_sms_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delivery_status_iam_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delivery_status_success_sampling_rate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monthly_spend_limit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usage_report_s3_bucket" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_sns_sms_preferences" "this" {
  default_sender_id                     = var.default_sender_id
  default_sms_type                      = var.default_sms_type
  delivery_status_iam_role_arn          = var.delivery_status_iam_role_arn
  delivery_status_success_sampling_rate = var.delivery_status_success_sampling_rate
  monthly_spend_limit                   = var.monthly_spend_limit
  usage_report_s3_bucket                = var.usage_report_s3_bucket
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_sns_sms_preferences.this.id
}

output "this" {
  value = aws_sns_sms_preferences.this
}
```

[top](#index)