# mso_schema_template_external_epg_selector

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
module "mso_schema_template_external_epg_selector" {
  source = "./modules/mso/d/mso_schema_template_external_epg_selector"

  # external_epg_name - (required) is a type of string
  external_epg_name = null
  # name - (required) is a type of string
  name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template_name - (required) is a type of string
  template_name = null

  expressions = [{
    key      = null
    operator = null
    value    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "external_epg_name" {
  description = "(required)"
  type        = string
}

variable "name" {
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

variable "expressions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key      = string
      operator = string
      value    = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_external_epg_selector" "this" {
  # external_epg_name - (required) is a type of string
  external_epg_name = var.external_epg_name
  # name - (required) is a type of string
  name = var.name
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # template_name - (required) is a type of string
  template_name = var.template_name

  dynamic "expressions" {
    for_each = var.expressions
    content {
      # key - (optional) is a type of string
      key = expressions.value["key"]
      # operator - (optional) is a type of string
      operator = expressions.value["operator"]
      # value - (optional) is a type of string
      value = expressions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_external_epg_selector.this.id
}

output "this" {
  value = mso_schema_template_external_epg_selector.this
}
```

[top](#index)