# aws_iam_account_alias

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
module "aws_iam_account_alias" {
  source = "./modules/aws/r/aws_iam_account_alias"

  # account_alias - (required) is a type of string
  account_alias = null
}
```

[top](#index)

### Variables

```terraform
variable "account_alias" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_account_alias" "this" {
  # account_alias - (required) is a type of string
  account_alias = var.account_alias
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iam_account_alias.this.id
}

output "this" {
  value = aws_iam_account_alias.this
}
```

[top](#index)