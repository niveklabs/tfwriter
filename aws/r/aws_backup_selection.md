# aws_backup_selection

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
module "aws_backup_selection" {
  source = "./modules/aws/r/aws_backup_selection"

  # iam_role_arn - (required) is a type of string
  iam_role_arn = null
  # name - (required) is a type of string
  name = null
  # plan_id - (required) is a type of string
  plan_id = null
  # resources - (optional) is a type of set of string
  resources = []

  selection_tag = [{
    key   = null
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "iam_role_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "plan_id" {
  description = "(required)"
  type        = string
}

variable "resources" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "selection_tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      type  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_backup_selection" "this" {
  # iam_role_arn - (required) is a type of string
  iam_role_arn = var.iam_role_arn
  # name - (required) is a type of string
  name = var.name
  # plan_id - (required) is a type of string
  plan_id = var.plan_id
  # resources - (optional) is a type of set of string
  resources = var.resources

  dynamic "selection_tag" {
    for_each = var.selection_tag
    content {
      # key - (required) is a type of string
      key = selection_tag.value["key"]
      # type - (required) is a type of string
      type = selection_tag.value["type"]
      # value - (required) is a type of string
      value = selection_tag.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_backup_selection.this.id
}

output "this" {
  value = aws_backup_selection.this
}
```

[top](#index)