# aws_signer_signing_profile_permission

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_signer_signing_profile_permission" {
  source = "./modules/aws/r/aws_signer_signing_profile_permission"

  # action - (required) is a type of string
  action = null
  # principal - (required) is a type of string
  principal = null
  # profile_name - (required) is a type of string
  profile_name = null
  # profile_version - (optional) is a type of string
  profile_version = null
  # statement_id - (optional) is a type of string
  statement_id = null
  # statement_id_prefix - (optional) is a type of string
  statement_id_prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required)"
  type        = string
}

variable "principal" {
  description = "(required)"
  type        = string
}

variable "profile_name" {
  description = "(required)"
  type        = string
}

variable "profile_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statement_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statement_id_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_signer_signing_profile_permission" "this" {
  action              = var.action
  principal           = var.principal
  profile_name        = var.profile_name
  profile_version     = var.profile_version
  statement_id        = var.statement_id
  statement_id_prefix = var.statement_id_prefix
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_signer_signing_profile_permission.this.id
}

output "profile_version" {
  description = "returns a string"
  value       = aws_signer_signing_profile_permission.this.profile_version
}

output "statement_id" {
  description = "returns a string"
  value       = aws_signer_signing_profile_permission.this.statement_id
}

output "this" {
  value = aws_signer_signing_profile_permission.this
}
```

[top](#index)