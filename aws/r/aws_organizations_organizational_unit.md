# aws_organizations_organizational_unit

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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

```hcl
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

```hcl
resource "aws_organizations_organizational_unit" "this" {
  name      = var.name
  parent_id = var.parent_id
}
```

[top](#index)

### Outputs

```hcl
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