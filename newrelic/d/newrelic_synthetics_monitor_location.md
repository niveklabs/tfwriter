# newrelic_synthetics_monitor_location

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
module "newrelic_synthetics_monitor_location" {
  source = "./modules/newrelic/d/newrelic_synthetics_monitor_location"

  # label - (required) is a type of string
  label = null
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(required) - The label of the Synthetics monitor location."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_synthetics_monitor_location" "this" {
  # label - (required) is a type of string
  label = var.label
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.newrelic_synthetics_monitor_location.this.description
}

output "high_security_mode" {
  description = "returns a bool"
  value       = data.newrelic_synthetics_monitor_location.this.high_security_mode
}

output "id" {
  description = "returns a string"
  value       = data.newrelic_synthetics_monitor_location.this.id
}

output "name" {
  description = "returns a string"
  value       = data.newrelic_synthetics_monitor_location.this.name
}

output "private" {
  description = "returns a bool"
  value       = data.newrelic_synthetics_monitor_location.this.private
}

output "this" {
  value = newrelic_synthetics_monitor_location.this
}
```

[top](#index)