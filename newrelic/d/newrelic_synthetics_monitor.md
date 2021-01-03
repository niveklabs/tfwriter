# newrelic_synthetics_monitor

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
module "newrelic_synthetics_monitor" {
  source = "./modules/newrelic/d/newrelic_synthetics_monitor"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the synthetics monitor in New Relic."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_synthetics_monitor" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.newrelic_synthetics_monitor.this.id
}

output "monitor_id" {
  description = "returns a string"
  value       = data.newrelic_synthetics_monitor.this.monitor_id
}

output "this" {
  value = newrelic_synthetics_monitor.this
}
```

[top](#index)