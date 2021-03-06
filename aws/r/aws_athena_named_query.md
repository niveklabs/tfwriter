# aws_athena_named_query

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
module "aws_athena_named_query" {
  source = "./modules/aws/r/aws_athena_named_query"

  # database - (required) is a type of string
  database = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
  # workgroup - (optional) is a type of string
  workgroup = null
}
```

[top](#index)

### Variables

```terraform
variable "database" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query" {
  description = "(required)"
  type        = string
}

variable "workgroup" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_athena_named_query" "this" {
  # database - (required) is a type of string
  database = var.database
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # query - (required) is a type of string
  query = var.query
  # workgroup - (optional) is a type of string
  workgroup = var.workgroup
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_athena_named_query.this.id
}

output "this" {
  value = aws_athena_named_query.this
}
```

[top](#index)