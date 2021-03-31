# aws_securityhub_organization_admin_account

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
module "aws_securityhub_organization_admin_account" {
  source = "./modules/aws/r/aws_securityhub_organization_admin_account"

  # admin_account_id - (required) is a type of string
  admin_account_id = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_account_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_securityhub_organization_admin_account" "this" {
  admin_account_id = var.admin_account_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_securityhub_organization_admin_account.this.id
}

output "this" {
  value = aws_securityhub_organization_admin_account.this
}
```

[top](#index)