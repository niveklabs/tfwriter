# mso_schema_template_contract

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_contract" {
  source = "./modules/mso/r/mso_schema_template_contract"

  # contract_name - (required) is a type of string
  contract_name = null
  # directives - (required) is a type of list of string
  directives = []
  # display_name - (optional) is a type of string
  display_name = null
  # filter_relationships - (required) is a type of map of string
  filter_relationships = {}
  # filter_type - (optional) is a type of string
  filter_type = null
  # schema_id - (required) is a type of string
  schema_id = null
  # scope - (optional) is a type of string
  scope = null
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "contract_name" {
  description = "(required)"
  type        = string
}

variable "directives" {
  description = "(required)"
  type        = list(string)
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_relationships" {
  description = "(required)"
  type        = map(string)
}

variable "filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_contract" "this" {
  contract_name        = var.contract_name
  directives           = var.directives
  display_name         = var.display_name
  filter_relationships = var.filter_relationships
  filter_type          = var.filter_type
  schema_id            = var.schema_id
  scope                = var.scope
  template_name        = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = mso_schema_template_contract.this.display_name
}

output "filter_type" {
  description = "returns a string"
  value       = mso_schema_template_contract.this.filter_type
}

output "id" {
  description = "returns a string"
  value       = mso_schema_template_contract.this.id
}

output "scope" {
  description = "returns a string"
  value       = mso_schema_template_contract.this.scope
}

output "this" {
  value = mso_schema_template_contract.this
}
```

[top](#index)