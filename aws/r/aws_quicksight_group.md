# aws_quicksight_group

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
module "aws_quicksight_group" {
  source = "./modules/aws/r/aws_quicksight_group"

  # aws_account_id - (optional) is a type of string
  aws_account_id = null
  # description - (optional) is a type of string
  description = null
  # group_name - (required) is a type of string
  group_name = null
  # namespace - (optional) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_quicksight_group" "this" {
  aws_account_id = var.aws_account_id
  description    = var.description
  group_name     = var.group_name
  namespace      = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_quicksight_group.this.arn
}

output "aws_account_id" {
  description = "returns a string"
  value       = aws_quicksight_group.this.aws_account_id
}

output "id" {
  description = "returns a string"
  value       = aws_quicksight_group.this.id
}

output "this" {
  value = aws_quicksight_group.this
}
```

[top](#index)