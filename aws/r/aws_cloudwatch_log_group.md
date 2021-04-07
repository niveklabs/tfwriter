# aws_cloudwatch_log_group

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
module "aws_cloudwatch_log_group" {
  source = "./modules/aws/r/aws_cloudwatch_log_group"

  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # retention_in_days - (optional) is a type of number
  retention_in_days = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "kms_key_id" {
  description = "(optional)"
  type        = string
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

variable "retention_in_days" {
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
resource "aws_cloudwatch_log_group" "this" {
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # retention_in_days - (optional) is a type of number
  retention_in_days = var.retention_in_days
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudwatch_log_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_log_group.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_cloudwatch_log_group.this.name
}

output "this" {
  value = aws_cloudwatch_log_group.this
}
```

[top](#index)