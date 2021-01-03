# mso_schema_template_contract_filter

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
module "mso_schema_template_contract_filter" {
  source = "./modules/mso/r/mso_schema_template_contract_filter"

  # contract_name - (required) is a type of string
  contract_name = null
  # directives - (required) is a type of list of string
  directives = []
  # filter_name - (required) is a type of string
  filter_name = null
  # filter_schema_id - (optional) is a type of string
  filter_schema_id = null
  # filter_template_name - (optional) is a type of string
  filter_template_name = null
  # filter_type - (required) is a type of string
  filter_type = null
  # schema_id - (required) is a type of string
  schema_id = null
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

variable "filter_name" {
  description = "(required)"
  type        = string
}

variable "filter_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_type" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_contract_filter" "this" {
  contract_name        = var.contract_name
  directives           = var.directives
  filter_name          = var.filter_name
  filter_schema_id     = var.filter_schema_id
  filter_template_name = var.filter_template_name
  filter_type          = var.filter_type
  schema_id            = var.schema_id
  template_name        = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "filter_schema_id" {
  description = "returns a string"
  value       = mso_schema_template_contract_filter.this.filter_schema_id
}

output "filter_template_name" {
  description = "returns a string"
  value       = mso_schema_template_contract_filter.this.filter_template_name
}

output "id" {
  description = "returns a string"
  value       = mso_schema_template_contract_filter.this.id
}

output "this" {
  value = mso_schema_template_contract_filter.this
}
```

[top](#index)