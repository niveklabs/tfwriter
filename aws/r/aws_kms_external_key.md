# aws_kms_external_key

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
module "aws_kms_external_key" {
  source = "./modules/aws/r/aws_kms_external_key"

  # deletion_window_in_days - (optional) is a type of number
  deletion_window_in_days = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # key_material_base64 - (optional) is a type of string
  key_material_base64 = null
  # policy - (optional) is a type of string
  policy = null
  # tags - (optional) is a type of map of string
  tags = {}
  # valid_to - (optional) is a type of string
  valid_to = null
}
```

[top](#index)

### Variables

```hcl
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

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_material_base64" {
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

variable "valid_to" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_kms_external_key" "this" {
  deletion_window_in_days = var.deletion_window_in_days
  description             = var.description
  enabled                 = var.enabled
  key_material_base64     = var.key_material_base64
  policy                  = var.policy
  tags                    = var.tags
  valid_to                = var.valid_to
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_kms_external_key.this.arn
}

output "enabled" {
  description = "returns a bool"
  value       = aws_kms_external_key.this.enabled
}

output "expiration_model" {
  description = "returns a string"
  value       = aws_kms_external_key.this.expiration_model
}

output "id" {
  description = "returns a string"
  value       = aws_kms_external_key.this.id
}

output "key_state" {
  description = "returns a string"
  value       = aws_kms_external_key.this.key_state
}

output "key_usage" {
  description = "returns a string"
  value       = aws_kms_external_key.this.key_usage
}

output "policy" {
  description = "returns a string"
  value       = aws_kms_external_key.this.policy
}

output "this" {
  value = aws_kms_external_key.this
}
```

[top](#index)