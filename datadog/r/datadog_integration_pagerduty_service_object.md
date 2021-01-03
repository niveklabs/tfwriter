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
    datadog = ">= 2.18.1"
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
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_pagerduty_service_object" "this" {
  service_key  = var.service_key
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