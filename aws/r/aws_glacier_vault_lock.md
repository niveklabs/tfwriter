# aws_glacier_vault_lock

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
module "aws_glacier_vault_lock" {
  source = "./modules/aws/r/aws_glacier_vault_lock"

  # complete_lock - (required) is a type of bool
  complete_lock = null
  # ignore_deletion_error - (optional) is a type of bool
  ignore_deletion_error = null
  # policy - (required) is a type of string
  policy = null
  # vault_name - (required) is a type of string
  vault_name = null
}
```

[top](#index)

### Variables

```terraform
variable "complete_lock" {
  description = "(required)"
  type        = bool
}

variable "ignore_deletion_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "policy" {
  description = "(required)"
  type        = string
}

variable "vault_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_glacier_vault_lock" "this" {
  # complete_lock - (required) is a type of bool
  complete_lock = var.complete_lock
  # ignore_deletion_error - (optional) is a type of bool
  ignore_deletion_error = var.ignore_deletion_error
  # policy - (required) is a type of string
  policy = var.policy
  # vault_name - (required) is a type of string
  vault_name = var.vault_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_glacier_vault_lock.this.id
}

output "this" {
  value = aws_glacier_vault_lock.this
}
```

[top](#index)