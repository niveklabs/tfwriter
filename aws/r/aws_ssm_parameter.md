# aws_ssm_parameter

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
module "aws_ssm_parameter" {
  source = "./modules/aws/r/aws_ssm_parameter"

  # allowed_pattern - (optional) is a type of string
  allowed_pattern = null
  # arn - (optional) is a type of string
  arn = null
  # data_type - (optional) is a type of string
  data_type = null
  # description - (optional) is a type of string
  description = null
  # key_id - (optional) is a type of string
  key_id = null
  # name - (required) is a type of string
  name = null
  # overwrite - (optional) is a type of bool
  overwrite = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tier - (optional) is a type of string
  tier = null
  # type - (required) is a type of string
  type = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "overwrite" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_parameter" "this" {
  # allowed_pattern - (optional) is a type of string
  allowed_pattern = var.allowed_pattern
  # arn - (optional) is a type of string
  arn = var.arn
  # data_type - (optional) is a type of string
  data_type = var.data_type
  # description - (optional) is a type of string
  description = var.description
  # key_id - (optional) is a type of string
  key_id = var.key_id
  # name - (required) is a type of string
  name = var.name
  # overwrite - (optional) is a type of bool
  overwrite = var.overwrite
  # tags - (optional) is a type of map of string
  tags = var.tags
  # tier - (optional) is a type of string
  tier = var.tier
  # type - (required) is a type of string
  type = var.type
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ssm_parameter.this.arn
}

output "data_type" {
  description = "returns a string"
  value       = aws_ssm_parameter.this.data_type
}

output "id" {
  description = "returns a string"
  value       = aws_ssm_parameter.this.id
}

output "key_id" {
  description = "returns a string"
  value       = aws_ssm_parameter.this.key_id
}

output "version" {
  description = "returns a number"
  value       = aws_ssm_parameter.this.version
}

output "this" {
  value = aws_ssm_parameter.this
}
```

[top](#index)