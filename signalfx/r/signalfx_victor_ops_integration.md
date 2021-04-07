# signalfx_victor_ops_integration

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
module "signalfx_victor_ops_integration" {
  source = "./modules/signalfx/r/signalfx_victor_ops_integration"

  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # post_url - (optional) is a type of string
  post_url = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required) - Whether the integration is enabled or not"
  type        = bool
}

variable "name" {
  description = "(required) - Name of the integration"
  type        = string
}

variable "post_url" {
  description = "(optional) - Opsgenie API URL for integration"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_victor_ops_integration" "this" {
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # post_url - (optional) is a type of string
  post_url = var.post_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_victor_ops_integration.this.id
}

output "this" {
  value = signalfx_victor_ops_integration.this
}
```

[top](#index)