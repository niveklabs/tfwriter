# aws_glue_catalog_database

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
module "aws_glue_catalog_database" {
  source = "./modules/aws/r/aws_glue_catalog_database"

  # catalog_id - (optional) is a type of string
  catalog_id = null
  # description - (optional) is a type of string
  description = null
  # location_uri - (optional) is a type of string
  location_uri = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_catalog_database" "this" {
  # catalog_id - (optional) is a type of string
  catalog_id = var.catalog_id
  # description - (optional) is a type of string
  description = var.description
  # location_uri - (optional) is a type of string
  location_uri = var.location_uri
  # name - (required) is a type of string
  name = var.name
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_catalog_database.this.arn
}

output "catalog_id" {
  description = "returns a string"
  value       = aws_glue_catalog_database.this.catalog_id
}

output "id" {
  description = "returns a string"
  value       = aws_glue_catalog_database.this.id
}

output "this" {
  value = aws_glue_catalog_database.this
}
```

[top](#index)