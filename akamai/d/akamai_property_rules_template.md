# akamai_property_rules_template

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_property_rules_template" {
  source = "./modules/akamai/d/akamai_property_rules_template"

  # template_file - (required) is a type of string
  template_file = null
  # var_definition_file - (optional) is a type of string
  var_definition_file = null
  # var_values_file - (optional) is a type of string
  var_values_file = null

  variables = [{
    name  = null
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "template_file" {
  description = "(required)"
  type        = string
}

variable "var_definition_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "var_values_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "variables" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      type  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "akamai_property_rules_template" "this" {
  # template_file - (required) is a type of string
  template_file = var.template_file
  # var_definition_file - (optional) is a type of string
  var_definition_file = var.var_definition_file
  # var_values_file - (optional) is a type of string
  var_values_file = var.var_values_file

  dynamic "variables" {
    for_each = var.variables
    content {
      # name - (required) is a type of string
      name = variables.value["name"]
      # type - (optional) is a type of string
      type = variables.value["type"]
      # value - (required) is a type of string
      value = variables.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_property_rules_template.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_property_rules_template.this.json
}

output "this" {
  value = akamai_property_rules_template.this
}
```

[top](#index)