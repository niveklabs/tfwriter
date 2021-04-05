# signalfx_opsgenie_integration

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
module "signalfx_opsgenie_integration" {
  source = "./modules/signalfx/r/signalfx_opsgenie_integration"

  # api_key - (required) is a type of string
  api_key = null
  # api_url - (optional) is a type of string
  api_url = null
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
  description = "(required) - Opsgenie API key"
  type        = string
}

variable "api_url" {
  description = "(optional) - Opsgenie API URL for integration"
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
resource "signalfx_opsgenie_integration" "this" {
  api_key = var.api_key
  api_url = var.api_url
  enabled = var.enabled
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_opsgenie_integration.this.id
}

output "this" {
  value = signalfx_opsgenie_integration.this
}
```

[top](#index)