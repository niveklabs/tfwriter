# aws_organizations_account

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
module "aws_organizations_account" {
  source = "./modules/aws/r/aws_organizations_account"

  # email - (required) is a type of string
  email = null
  # iam_user_access_to_billing - (optional) is a type of string
  iam_user_access_to_billing = null
  # name - (required) is a type of string
  name = null
  # parent_id - (optional) is a type of string
  parent_id = null
  # role_name - (optional) is a type of string
  role_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}

variable "iam_user_access_to_billing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_name" {
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

```terraform
resource "aws_organizations_account" "this" {
  email                      = var.email
  iam_user_access_to_billing = var.iam_user_access_to_billing
  name                       = var.name
  parent_id                  = var.parent_id
  role_name                  = var.role_name
  tags                       = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_organizations_account.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_organizations_account.this.id
}

output "joined_method" {
  description = "returns a string"
  value       = aws_organizations_account.this.joined_method
}

output "joined_timestamp" {
  description = "returns a string"
  value       = aws_organizations_account.this.joined_timestamp
}

output "parent_id" {
  description = "returns a string"
  value       = aws_organizations_account.this.parent_id
}

output "status" {
  description = "returns a string"
  value       = aws_organizations_account.this.status
}

output "this" {
  value = aws_organizations_account.this
}
```

[top](#index)