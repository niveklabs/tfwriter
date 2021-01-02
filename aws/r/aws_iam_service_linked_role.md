# aws_iam_service_linked_role

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_iam_service_linked_role" {
  source = "./modules/aws/r/aws_iam_service_linked_role"

  # aws_service_name - (required) is a type of string
  aws_service_name = null
  # custom_suffix - (optional) is a type of string
  custom_suffix = null
  # description - (optional) is a type of string
  description = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_service_name" {
  description = "(required)"
  type        = string
}

variable "custom_suffix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_service_linked_role" "this" {
  aws_service_name = var.aws_service_name
  custom_suffix    = var.custom_suffix
  description      = var.description
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iam_service_linked_role.this.arn
}

output "create_date" {
  description = "returns a string"
  value       = aws_iam_service_linked_role.this.create_date
}

output "id" {
  description = "returns a string"
  value       = aws_iam_service_linked_role.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_service_linked_role.this.name
}

output "path" {
  description = "returns a string"
  value       = aws_iam_service_linked_role.this.path
}

output "unique_id" {
  description = "returns a string"
  value       = aws_iam_service_linked_role.this.unique_id
}

output "this" {
  value = aws_iam_service_linked_role.this
}
```

[top](#index)