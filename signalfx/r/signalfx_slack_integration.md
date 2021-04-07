# signalfx_slack_integration

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
module "signalfx_slack_integration" {
  source = "./modules/signalfx/r/signalfx_slack_integration"

  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # webhook_url - (required) is a type of string
  webhook_url = null
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

variable "webhook_url" {
  description = "(required) - Slack Webhook URL for integration"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_slack_integration" "this" {
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # webhook_url - (required) is a type of string
  webhook_url = var.webhook_url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_slack_integration.this.id
}

output "this" {
  value = signalfx_slack_integration.this
}
```

[top](#index)