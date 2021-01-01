# aws_iam_account_alias

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
module "aws_iam_account_alias" {
  source = "./modules/aws/r/aws_iam_account_alias"

  # account_alias - (required) is a type of string
  account_alias = null
}
```

[top](#index)

### Variables

```hcl
variable "account_alias" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_iam_account_alias" "this" {
  account_alias = var.account_alias
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_iam_account_alias.this.id
}

output "this" {
  value = aws_iam_account_alias.this
}
```

[top](#index)