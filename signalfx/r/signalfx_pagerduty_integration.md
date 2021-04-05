# signalfx_pagerduty_integration

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_pagerduty_integration" {
  source = "./modules/signalfx/r/signalfx_pagerduty_integration"

  # api_key - (optional) is a type of string
  api_key = null
  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "api_key" {
  description = "(optional) - PagerDuty API key"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(required) - Whether the integration is enabled or not"
  type        = bool
}

variable "name" {
  description = "(required) - Name of the integration"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_pagerduty_integration" "this" {
  api_key = var.api_key
  enabled = var.enabled
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_pagerduty_integration.this.id
}

output "this" {
  value = signalfx_pagerduty_integration.this
}
```

[top](#index)