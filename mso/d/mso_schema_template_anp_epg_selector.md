# mso_schema_template_anp_epg_selector

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
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_anp_epg_selector" {
  source = "./modules/mso/d/mso_schema_template_anp_epg_selector"

  # anp_name - (required) is a type of string
  anp_name = null
  # epg_name - (required) is a type of string
  epg_name = null
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
variable "anp_name" {
  description = "(required)"
  type        = string
}

variable "epg_name" {
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
data "mso_schema_template_anp_epg_selector" "this" {
  anp_name      = var.anp_name
  epg_name      = var.epg_name
  name          = var.name
  schema_id     = var.schema_id
  template_name = var.template_name

  dynamic "expressions" {
    for_each = var.expressions
    content {
      key      = expressions.value["key"]
      operator = expressions.value["operator"]
      value    = expressions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg_selector.this.id
}

output "this" {
  value = mso_schema_template_anp_epg_selector.this
}
```

[top](#index)