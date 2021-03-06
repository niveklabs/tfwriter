# aws_backup_plan

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_backup_plan" {
  source = "./modules/aws/d/aws_backup_plan"

  # plan_id - (required) is a type of string
  plan_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "plan_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_backup_plan" "this" {
  # plan_id - (required) is a type of string
  plan_id = var.plan_id
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.name
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_backup_plan.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.aws_backup_plan.this.version
}

output "this" {
  value = aws_backup_plan.this
}
```

[top](#index)