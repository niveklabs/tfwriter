# aws_kms_key

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
module "aws_kms_key" {
  source = "./modules/aws/r/aws_kms_key"

  # customer_master_key_spec - (optional) is a type of string
  customer_master_key_spec = null
  # deletion_window_in_days - (optional) is a type of number
  deletion_window_in_days = null
  # description - (optional) is a type of string
  description = null
  # enable_key_rotation - (optional) is a type of bool
  enable_key_rotation = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # key_usage - (optional) is a type of string
  key_usage = null
  # policy - (optional) is a type of string
  policy = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "customer_master_key_spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_window_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_key_rotation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_usage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
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

```hcl
resource "aws_kms_key" "this" {
  customer_master_key_spec = var.customer_master_key_spec
  deletion_window_in_days  = var.deletion_window_in_days
  description              = var.description
  enable_key_rotation      = var.enable_key_rotation
  is_enabled               = var.is_enabled
  key_usage                = var.key_usage
  policy                   = var.policy
  tags                     = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_kms_key.this.arn
}

output "description" {
  description = "returns a string"
  value       = aws_kms_key.this.description
}

output "id" {
  description = "returns a string"
  value       = aws_kms_key.this.id
}

output "key_id" {
  description = "returns a string"
  value       = aws_kms_key.this.key_id
}

output "policy" {
  description = "returns a string"
  value       = aws_kms_key.this.policy
}

output "this" {
  value = aws_kms_key.this
}
```

[top](#index)