# sumologic_field_extraction_rule

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_field_extraction_rule" {
  source = "./modules/sumologic/r/sumologic_field_extraction_rule"

  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # parse_expression - (required) is a type of string
  parse_expression = null
  # scope - (required) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parse_expression" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_field_extraction_rule" "this" {
  enabled          = var.enabled
  name             = var.name
  parse_expression = var.parse_expression
  scope            = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_field_extraction_rule.this.id
}

output "this" {
  value = sumologic_field_extraction_rule.this
}
```

[top](#index)