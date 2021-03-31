# aws_securityhub_action_target

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_securityhub_action_target" {
  source = "./modules/aws/r/aws_securityhub_action_target"

  # description - (required) is a type of string
  description = null
  # identifier - (required) is a type of string
  identifier = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "identifier" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_securityhub_action_target" "this" {
  description = var.description
  identifier  = var.identifier
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_securityhub_action_target.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_securityhub_action_target.this.id
}

output "this" {
  value = aws_securityhub_action_target.this
}
```

[top](#index)