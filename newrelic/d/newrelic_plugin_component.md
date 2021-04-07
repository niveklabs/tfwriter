# newrelic_plugin_component

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_plugin_component" {
  source = "./modules/newrelic/d/newrelic_plugin_component"

  # name - (required) is a type of string
  name = null
  # plugin_id - (required) is a type of number
  plugin_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the plugin component."
  type        = string
}

variable "plugin_id" {
  description = "(required) - The ID of the plugin instance this component belongs to."
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_plugin_component" "this" {
  # name - (required) is a type of string
  name = var.name
  # plugin_id - (required) is a type of number
  plugin_id = var.plugin_id
}
```

[top](#index)

### Outputs

```terraform
output "health_status" {
  description = "returns a string"
  value       = data.newrelic_plugin_component.this.health_status
}

output "id" {
  description = "returns a string"
  value       = data.newrelic_plugin_component.this.id
}

output "this" {
  value = newrelic_plugin_component.this
}
```

[top](#index)