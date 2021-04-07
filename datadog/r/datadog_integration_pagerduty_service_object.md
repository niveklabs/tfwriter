# datadog_integration_pagerduty_service_object

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_integration_pagerduty_service_object" {
  source = "./modules/datadog/r/datadog_integration_pagerduty_service_object"

  # service_key - (required) is a type of string
  service_key = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "service_key" {
  description = "(required) - Your Service name associated service key in PagerDuty. Note: Since the Datadog API never returns service keys, it is impossible to detect [drifts](https://www.hashicorp.com/blog/detecting-and-managing-drift-with-terraform). The best way to solve a drift is to manually mark the Service Object resource with [terraform taint](https://www.terraform.io/docs/commands/taint.html) to have it destroyed and recreated."
  type        = string
}

variable "service_name" {
  description = "(required) - Your Service name in PagerDuty."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_pagerduty_service_object" "this" {
  # service_key - (required) is a type of string
  service_key = var.service_key
  # service_name - (required) is a type of string
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_pagerduty_service_object.this.id
}

output "this" {
  value = datadog_integration_pagerduty_service_object.this
}
```

[top](#index)