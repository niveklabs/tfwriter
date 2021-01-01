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
  source = "./modules/aws/d/aws_iam_account_alias"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Datasource

```hcl
data "aws_iam_account_alias" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "account_alias" {
  description = "returns a string"
  value       = data.aws_iam_account_alias.this.account_alias
}

output "id" {
  description = "returns a string"
  value       = data.aws_iam_account_alias.this.id
}

output "this" {
  value = aws_iam_account_alias.this
}
```

[top](#index)