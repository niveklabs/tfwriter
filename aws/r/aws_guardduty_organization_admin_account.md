# aws_guardduty_organization_admin_account

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_guardduty_organization_admin_account" {
  source = "./modules/aws/r/aws_guardduty_organization_admin_account"

  # admin_account_id - (required) is a type of string
  admin_account_id = null
}
```

[top](#index)

### Variables

```hcl
variable "admin_account_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_guardduty_organization_admin_account" "this" {
  admin_account_id = var.admin_account_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_guardduty_organization_admin_account.this.id
}

output "this" {
  value = aws_guardduty_organization_admin_account.this
}
```

[top](#index)