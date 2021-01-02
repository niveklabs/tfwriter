# aws_sqs_queue

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
module "aws_sqs_queue" {
  source = "./modules/aws/r/aws_sqs_queue"

  # content_based_deduplication - (optional) is a type of bool
  content_based_deduplication = null
  # delay_seconds - (optional) is a type of number
  delay_seconds = null
  # fifo_queue - (optional) is a type of bool
  fifo_queue = null
  # kms_data_key_reuse_period_seconds - (optional) is a type of number
  kms_data_key_reuse_period_seconds = null
  # kms_master_key_id - (optional) is a type of string
  kms_master_key_id = null
  # max_message_size - (optional) is a type of number
  max_message_size = null
  # message_retention_seconds - (optional) is a type of number
  message_retention_seconds = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # policy - (optional) is a type of string
  policy = null
  # receive_wait_time_seconds - (optional) is a type of number
  receive_wait_time_seconds = null
  # redrive_policy - (optional) is a type of string
  redrive_policy = null
  # tags - (optional) is a type of map of string
  tags = {}
  # visibility_timeout_seconds - (optional) is a type of number
  visibility_timeout_seconds = null
}
```

[top](#index)

### Variables

```terraform
variable "content_based_deduplication" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "delay_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fifo_queue" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_data_key_reuse_period_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kms_master_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_message_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "message_retention_seconds" {
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

variable "receive_wait_time_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "redrive_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "visibility_timeout_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_sqs_queue" "this" {
  content_based_deduplication       = var.content_based_deduplication
  delay_seconds                     = var.delay_seconds
  fifo_queue                        = var.fifo_queue
  kms_data_key_reuse_period_seconds = var.kms_data_key_reuse_period_seconds
  kms_master_key_id                 = var.kms_master_key_id
  max_message_size                  = var.max_message_size
  message_retention_seconds         = var.message_retention_seconds
  name                              = var.name
  name_prefix                       = var.name_prefix
  policy                            = var.policy
  receive_wait_time_seconds         = var.receive_wait_time_seconds
  redrive_policy                    = var.redrive_policy
  tags                              = var.tags
  visibility_timeout_seconds        = var.visibility_timeout_seconds
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sqs_queue.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sqs_queue.this.id
}

output "kms_data_key_reuse_period_seconds" {
  description = "returns a number"
  value       = aws_sqs_queue.this.kms_data_key_reuse_period_seconds
}

output "name" {
  description = "returns a string"
  value       = aws_sqs_queue.this.name
}

output "policy" {
  description = "returns a string"
  value       = aws_sqs_queue.this.policy
}

output "this" {
  value = aws_sqs_queue.this
}
```

[top](#index)