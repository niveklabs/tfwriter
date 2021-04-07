# newrelic_alert_channel

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
module "newrelic_alert_channel" {
  source = "./modules/newrelic/d/newrelic_alert_channel"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the alert channel in New Relic."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_alert_channel" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "config" {
  description = "returns a list of object"
  value       = data.newrelic_alert_channel.this.config
}

output "id" {
  description = "returns a string"
  value       = data.newrelic_alert_channel.this.id
}

output "policy_ids" {
  description = "returns a list of number"
  value       = data.newrelic_alert_channel.this.policy_ids
}

output "type" {
  description = "returns a string"
  value       = data.newrelic_alert_channel.this.type
}

output "this" {
  value = newrelic_alert_channel.this
}
```

[top](#index)