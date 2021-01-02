# aws_organizations_organization

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/aws/d/aws_organizations_organization"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_organizations_organization" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "accounts" {
  description = "returns a list of object"
  value       = data.aws_organizations_organization.this.accounts
}

output "arn" {
  description = "returns a string"
  value       = data.aws_organizations_organization.this.arn
}

output "aws_service_access_principals" {
  description = "returns a set of string"
  value       = data.aws_organizations_organization.this.aws_service_access_principals
}

output "enabled_policy_types" {
  description = "returns a set of string"
  value       = data.aws_organizations_organization.this.enabled_policy_types
}

output "feature_set" {
  description = "returns a string"
  value       = data.aws_organizations_organization.this.feature_set
}

output "id" {
  description = "returns a string"
  value       = data.aws_organizations_organization.this.id
}

output "master_account_arn" {
  description = "returns a string"
  value       = data.aws_organizations_organization.this.master_account_arn
}

output "master_account_email" {
  description = "returns a string"
  value       = data.aws_organizations_organization.this.master_account_email
}

output "master_account_id" {
  description = "returns a string"
  value       = data.aws_organizations_organization.this.master_account_id
}

output "non_master_accounts" {
  description = "returns a list of object"
  value       = data.aws_organizations_organization.this.non_master_accounts
}

output "roots" {
  description = "returns a list of object"
  value       = data.aws_organizations_organization.this.roots
}

output "this" {
  value = aws_organizations_organization.this
}
```

[top](#index)