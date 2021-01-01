# aws_lex_slot_type

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_lex_slot_type" {
  source = "./modules/aws/d/aws_lex_slot_type"

  # name - (required) is a type of string
  name = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_lex_slot_type" "this" {
  name    = var.name
  version = var.version
}
```

[top](#index)

### Outputs

```hcl
output "checksum" {
  description = "returns a string"
  value       = data.aws_lex_slot_type.this.checksum
}

output "created_date" {
  description = "returns a string"
  value       = data.aws_lex_slot_type.this.created_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_lex_slot_type.this.description
}

output "enumeration_value" {
  description = "returns a set of object"
  value       = data.aws_lex_slot_type.this.enumeration_value
}

output "id" {
  description = "returns a string"
  value       = data.aws_lex_slot_type.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = data.aws_lex_slot_type.this.last_updated_date
}

output "value_selection_strategy" {
  description = "returns a string"
  value       = data.aws_lex_slot_type.this.value_selection_strategy
}

output "this" {
  value = aws_lex_slot_type.this
}
```

[top](#index)