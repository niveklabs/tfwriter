# aws_organizations_organization

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
module "aws_organizations_organization" {
  source = "./modules/aws/r/aws_organizations_organization"

  # aws_service_access_principals - (optional) is a type of set of string
  aws_service_access_principals = []
  # enabled_policy_types - (optional) is a type of set of string
  enabled_policy_types = []
  # feature_set - (optional) is a type of string
  feature_set = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_service_access_principals" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "enabled_policy_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "feature_set" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_organizations_organization" "this" {
  aws_service_access_principals = var.aws_service_access_principals
  enabled_policy_types          = var.enabled_policy_types
  feature_set                   = var.feature_set
}
```

[top](#index)

### Outputs

```terraform
output "accounts" {
  description = "returns a list of object"
  value       = aws_organizations_organization.this.accounts
}

output "arn" {
  description = "returns a string"
  value       = aws_organizations_organization.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_organizations_organization.this.id
}

output "master_account_arn" {
  description = "returns a string"
  value       = aws_organizations_organization.this.master_account_arn
}

output "master_account_email" {
  description = "returns a string"
  value       = aws_organizations_organization.this.master_account_email
}

output "master_account_id" {
  description = "returns a string"
  value       = aws_organizations_organization.this.master_account_id
}

output "non_master_accounts" {
  description = "returns a list of object"
  value       = aws_organizations_organization.this.non_master_accounts
}

output "roots" {
  description = "returns a list of object"
  value       = aws_organizations_organization.this.roots
}

output "this" {
  value = aws_organizations_organization.this
}
```

[top](#index)