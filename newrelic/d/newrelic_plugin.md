# newrelic_plugin

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
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_plugin" {
  source = "./modules/newrelic/d/newrelic_plugin"

  # guid - (required) is a type of string
  guid = null
}
```

[top](#index)

### Variables

```terraform
variable "guid" {
  description = "(required) - The GUID of the plugin in New Relic."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_plugin" "this" {
  guid = var.guid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.newrelic_plugin.this.id
}

output "this" {
  value = newrelic_plugin.this
}
```

[top](#index)