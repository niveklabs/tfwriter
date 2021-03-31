# aws_iam_group

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
module "aws_iam_group" {
  source = "./modules/aws/d/aws_iam_group"

  # group_name - (required) is a type of string
  group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_iam_group" "this" {
  group_name = var.group_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_iam_group.this.arn
}

output "group_id" {
  description = "returns a string"
  value       = data.aws_iam_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_iam_group.this.id
}

output "path" {
  description = "returns a string"
  value       = data.aws_iam_group.this.path
}

output "users" {
  description = "returns a list of object"
  value       = data.aws_iam_group.this.users
}

output "this" {
  value = aws_iam_group.this
}
```

[top](#index)