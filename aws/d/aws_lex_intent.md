# aws_lex_intent

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
module "aws_lex_intent" {
  source = "./modules/aws/d/aws_lex_intent"

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
data "aws_lex_intent" "this" {
  name    = var.name
  version = var.version
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_lex_intent.this.arn
}

output "checksum" {
  description = "returns a string"
  value       = data.aws_lex_intent.this.checksum
}

output "created_date" {
  description = "returns a string"
  value       = data.aws_lex_intent.this.created_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_lex_intent.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_lex_intent.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = data.aws_lex_intent.this.last_updated_date
}

output "parent_intent_signature" {
  description = "returns a string"
  value       = data.aws_lex_intent.this.parent_intent_signature
}

output "this" {
  value = aws_lex_intent.this
}
```

[top](#index)