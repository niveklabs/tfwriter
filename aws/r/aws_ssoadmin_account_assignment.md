# aws_ssoadmin_account_assignment

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
module "aws_ssoadmin_account_assignment" {
  source = "./modules/aws/r/aws_ssoadmin_account_assignment"

  # instance_arn - (required) is a type of string
  instance_arn = null
  # permission_set_arn - (required) is a type of string
  permission_set_arn = null
  # principal_id - (required) is a type of string
  principal_id = null
  # principal_type - (required) is a type of string
  principal_type = null
  # target_id - (required) is a type of string
  target_id = null
  # target_type - (optional) is a type of string
  target_type = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_arn" {
  description = "(required)"
  type        = string
}

variable "permission_set_arn" {
  description = "(required)"
  type        = string
}

variable "principal_id" {
  description = "(required)"
  type        = string
}

variable "principal_type" {
  description = "(required)"
  type        = string
}

variable "target_id" {
  description = "(required)"
  type        = string
}

variable "target_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssoadmin_account_assignment" "this" {
  # instance_arn - (required) is a type of string
  instance_arn = var.instance_arn
  # permission_set_arn - (required) is a type of string
  permission_set_arn = var.permission_set_arn
  # principal_id - (required) is a type of string
  principal_id = var.principal_id
  # principal_type - (required) is a type of string
  principal_type = var.principal_type
  # target_id - (required) is a type of string
  target_id = var.target_id
  # target_type - (optional) is a type of string
  target_type = var.target_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssoadmin_account_assignment.this.id
}

output "this" {
  value = aws_ssoadmin_account_assignment.this
}
```

[top](#index)