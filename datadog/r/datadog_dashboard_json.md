# datadog_dashboard_json

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
module "datadog_dashboard_json" {
  source = "./modules/datadog/r/datadog_dashboard_json"

  # dashboard - (required) is a type of string
  dashboard = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "dashboard" {
  description = "(required) - The JSON formatted definition of the Dashboard."
  type        = string
}

variable "url" {
  description = "(optional) - The URL of the dashboard."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_dashboard_json" "this" {
  # dashboard - (required) is a type of string
  dashboard = var.dashboard
  # url - (optional) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_dashboard_json.this.id
}

output "url" {
  description = "returns a string"
  value       = datadog_dashboard_json.this.url
}

output "this" {
  value = datadog_dashboard_json.this
}
```

[top](#index)