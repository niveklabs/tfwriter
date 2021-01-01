# aws_cognito_user_pools

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
module "aws_cognito_user_pools" {
  source = "./modules/aws/d/aws_cognito_user_pools"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_cognito_user_pools" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "arns" {
  description = "returns a set of string"
  value       = data.aws_cognito_user_pools.this.arns
}

output "id" {
  description = "returns a string"
  value       = data.aws_cognito_user_pools.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.aws_cognito_user_pools.this.ids
}

output "this" {
  value = aws_cognito_user_pools.this
}
```

[top](#index)