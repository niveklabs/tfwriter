# aws_organizations_organizational_unit

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
module "aws_organizations_organizational_unit" {
  source = "./modules/aws/r/aws_organizations_organizational_unit"

  # name - (required) is a type of string
  name = null
  # parent_id - (required) is a type of string
  parent_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_organizations_organizational_unit" "this" {
  # name - (required) is a type of string
  name = var.name
  # parent_id - (required) is a type of string
  parent_id = var.parent_id
}
```

[top](#index)

### Outputs

```terraform
output "accounts" {
  description = "returns a list of object"
  value       = aws_organizations_organizational_unit.this.accounts
}

output "arn" {
  description = "returns a string"
  value       = aws_organizations_organizational_unit.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_organizations_organizational_unit.this.id
}

output "this" {
  value = aws_organizations_organizational_unit.this
}
```

[top](#index)