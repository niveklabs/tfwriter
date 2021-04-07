# signalfx_webhook_integration

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
module "signalfx_webhook_integration" {
  source = "./modules/signalfx/r/signalfx_webhook_integration"

  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # shared_secret - (optional) is a type of string
  shared_secret = null
  # url - (optional) is a type of string
  url = null

  headers = [{
    header_key   = null
    header_value = null
  }]
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

variable "shared_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(optional) - Webhook URL"
  type        = string
  default     = null
}

variable "headers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      header_key   = string
      header_value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_webhook_integration" "this" {
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # shared_secret - (optional) is a type of string
  shared_secret = var.shared_secret
  # url - (optional) is a type of string
  url = var.url

  dynamic "headers" {
    for_each = var.headers
    content {
      # header_key - (required) is a type of string
      header_key = headers.value["header_key"]
      # header_value - (required) is a type of string
      header_value = headers.value["header_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_webhook_integration.this.id
}

output "this" {
  value = signalfx_webhook_integration.this
}
```

[top](#index)