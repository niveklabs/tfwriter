# aws_sns_topic

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_sns_topic" {
  source = "./modules/aws/r/aws_sns_topic"

  # application_failure_feedback_role_arn - (optional) is a type of string
  application_failure_feedback_role_arn = null
  # application_success_feedback_role_arn - (optional) is a type of string
  application_success_feedback_role_arn = null
  # application_success_feedback_sample_rate - (optional) is a type of number
  application_success_feedback_sample_rate = null
  # delivery_policy - (optional) is a type of string
  delivery_policy = null
  # display_name - (optional) is a type of string
  display_name = null
  # http_failure_feedback_role_arn - (optional) is a type of string
  http_failure_feedback_role_arn = null
  # http_success_feedback_role_arn - (optional) is a type of string
  http_success_feedback_role_arn = null
  # http_success_feedback_sample_rate - (optional) is a type of number
  http_success_feedback_sample_rate = null
  # kms_master_key_id - (optional) is a type of string
  kms_master_key_id = null
  # lambda_failure_feedback_role_arn - (optional) is a type of string
  lambda_failure_feedback_role_arn = null
  # lambda_success_feedback_role_arn - (optional) is a type of string
  lambda_success_feedback_role_arn = null
  # lambda_success_feedback_sample_rate - (optional) is a type of number
  lambda_success_feedback_sample_rate = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # policy - (optional) is a type of string
  policy = null
  # sqs_failure_feedback_role_arn - (optional) is a type of string
  sqs_failure_feedback_role_arn = null
  # sqs_success_feedback_role_arn - (optional) is a type of string
  sqs_success_feedback_role_arn = null
  # sqs_success_feedback_sample_rate - (optional) is a type of number
  sqs_success_feedback_sample_rate = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "application_failure_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_success_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_success_feedback_sample_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "delivery_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_failure_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_success_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_success_feedback_sample_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kms_master_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lambda_failure_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lambda_success_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lambda_success_feedback_sample_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sqs_failure_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sqs_success_feedback_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sqs_success_feedback_sample_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_sns_topic" "this" {
  application_failure_feedback_role_arn    = var.application_failure_feedback_role_arn
  application_success_feedback_role_arn    = var.application_success_feedback_role_arn
  application_success_feedback_sample_rate = var.application_success_feedback_sample_rate
  delivery_policy                          = var.delivery_policy
  display_name                             = var.display_name
  http_failure_feedback_role_arn           = var.http_failure_feedback_role_arn
  http_success_feedback_role_arn           = var.http_success_feedback_role_arn
  http_success_feedback_sample_rate        = var.http_success_feedback_sample_rate
  kms_master_key_id                        = var.kms_master_key_id
  lambda_failure_feedback_role_arn         = var.lambda_failure_feedback_role_arn
  lambda_success_feedback_role_arn         = var.lambda_success_feedback_role_arn
  lambda_success_feedback_sample_rate      = var.lambda_success_feedback_sample_rate
  name                                     = var.name
  name_prefix                              = var.name_prefix
  policy                                   = var.policy
  sqs_failure_feedback_role_arn            = var.sqs_failure_feedback_role_arn
  sqs_success_feedback_role_arn            = var.sqs_success_feedback_role_arn
  sqs_success_feedback_sample_rate         = var.sqs_success_feedback_sample_rate
  tags                                     = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sns_topic.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sns_topic.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_sns_topic.this.name
}

output "policy" {
  description = "returns a string"
  value       = aws_sns_topic.this.policy
}

output "this" {
  value = aws_sns_topic.this
}
```

[top](#index)