# aws_glue_schema

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
module "aws_glue_schema" {
  source = "./modules/aws/r/aws_glue_schema"

  # compatibility - (required) is a type of string
  compatibility = null
  # data_format - (required) is a type of string
  data_format = null
  # description - (optional) is a type of string
  description = null
  # registry_arn - (optional) is a type of string
  registry_arn = null
  # schema_definition - (required) is a type of string
  schema_definition = null
  # schema_name - (required) is a type of string
  schema_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "compatibility" {
  description = "(required)"
  type        = string
}

variable "data_format" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "registry_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_definition" {
  description = "(required)"
  type        = string
}

variable "schema_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_schema" "this" {
  compatibility     = var.compatibility
  data_format       = var.data_format
  description       = var.description
  registry_arn      = var.registry_arn
  schema_definition = var.schema_definition
  schema_name       = var.schema_name
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_schema.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_glue_schema.this.id
}

output "latest_schema_version" {
  description = "returns a number"
  value       = aws_glue_schema.this.latest_schema_version
}

output "next_schema_version" {
  description = "returns a number"
  value       = aws_glue_schema.this.next_schema_version
}

output "registry_arn" {
  description = "returns a string"
  value       = aws_glue_schema.this.registry_arn
}

output "registry_name" {
  description = "returns a string"
  value       = aws_glue_schema.this.registry_name
}

output "schema_checkpoint" {
  description = "returns a number"
  value       = aws_glue_schema.this.schema_checkpoint
}

output "this" {
  value = aws_glue_schema.this
}
```

[top](#index)