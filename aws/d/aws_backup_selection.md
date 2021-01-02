# aws_backup_selection

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
module "aws_backup_selection" {
  source = "./modules/aws/d/aws_backup_selection"

  # plan_id - (required) is a type of string
  plan_id = null
  # selection_id - (required) is a type of string
  selection_id = null
}
```

[top](#index)

### Variables

```terraform
variable "plan_id" {
  description = "(required)"
  type        = string
}

variable "selection_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_backup_selection" "this" {
  plan_id      = var.plan_id
  selection_id = var.selection_id
}
```

[top](#index)

### Outputs

```terraform
output "iam_role_arn" {
  description = "returns a string"
  value       = data.aws_backup_selection.this.iam_role_arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_backup_selection.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_backup_selection.this.name
}

output "resources" {
  description = "returns a set of string"
  value       = data.aws_backup_selection.this.resources
}

output "this" {
  value = aws_backup_selection.this
}
```

[top](#index)