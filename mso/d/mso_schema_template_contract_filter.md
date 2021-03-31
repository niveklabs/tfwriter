# mso_schema_template_contract_filter

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_contract_filter" {
  source = "./modules/mso/d/mso_schema_template_contract_filter"

  # contract_name - (required) is a type of string
  contract_name = null
  # directives - (optional) is a type of list of string
  directives = []
  # filter_name - (required) is a type of string
  filter_name = null
  # filter_schema_id - (required) is a type of string
  filter_schema_id = null
  # filter_template_name - (required) is a type of string
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
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "filter_name" {
  description = "(required)"
  type        = string
}

variable "filter_schema_id" {
  description = "(required)"
  type        = string
}

variable "filter_template_name" {
  description = "(required)"
  type        = string
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

### Datasource

```terraform
data "mso_schema_template_contract_filter" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_contract_filter.this.id
}

output "this" {
  value = mso_schema_template_contract_filter.this
}
```

[top](#index)