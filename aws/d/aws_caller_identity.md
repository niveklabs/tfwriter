# aws_caller_identity

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_caller_identity" {
  source = "./modules/aws/d/aws_caller_identity"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_caller_identity" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = data.aws_caller_identity.this.account_id
}

output "arn" {
  description = "returns a string"
  value       = data.aws_caller_identity.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_caller_identity.this.id
}

output "user_id" {
  description = "returns a string"
  value       = data.aws_caller_identity.this.user_id
}

output "this" {
  value = aws_caller_identity.this
}
```

[top](#index)