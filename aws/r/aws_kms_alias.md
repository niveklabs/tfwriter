# aws_kms_alias

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
module "aws_kms_alias" {
  source = "./modules/aws/r/aws_kms_alias"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # target_key_id - (required) is a type of string
  target_key_id = null
}
```

[top](#index)

### Variables

```terraform
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

variable "target_key_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_kms_alias" "this" {
  name          = var.name
  name_prefix   = var.name_prefix
  target_key_id = var.target_key_id
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_kms_alias.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_kms_alias.this.id
}

output "target_key_arn" {
  description = "returns a string"
  value       = aws_kms_alias.this.target_key_arn
}

output "this" {
  value = aws_kms_alias.this
}
```

[top](#index)