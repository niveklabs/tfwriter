# pagerduty_service_integration

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_service_integration" {
  source = "./modules/pagerduty/r/pagerduty_service_integration"

  # integration_email - (optional) is a type of string
  integration_email = null
  # integration_key - (optional) is a type of string
  integration_key = null
  # name - (optional) is a type of string
  name = null
  # service - (required) is a type of string
  service = null
  # type - (optional) is a type of string
  type = null
  # vendor - (optional) is a type of string
  vendor = null
}
```

[top](#index)

### Variables

```terraform
variable "integration_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "integration_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vendor" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_service_integration" "this" {
  # integration_email - (optional) is a type of string
  integration_email = var.integration_email
  # integration_key - (optional) is a type of string
  integration_key = var.integration_key
  # name - (optional) is a type of string
  name = var.name
  # service - (required) is a type of string
  service = var.service
  # type - (optional) is a type of string
  type = var.type
  # vendor - (optional) is a type of string
  vendor = var.vendor
}
```

[top](#index)

### Outputs

```terraform
output "html_url" {
  description = "returns a string"
  value       = pagerduty_service_integration.this.html_url
}

output "id" {
  description = "returns a string"
  value       = pagerduty_service_integration.this.id
}

output "integration_email" {
  description = "returns a string"
  value       = pagerduty_service_integration.this.integration_email
}

output "integration_key" {
  description = "returns a string"
  value       = pagerduty_service_integration.this.integration_key
}

output "type" {
  description = "returns a string"
  value       = pagerduty_service_integration.this.type
}

output "vendor" {
  description = "returns a string"
  value       = pagerduty_service_integration.this.vendor
}

output "this" {
  value = pagerduty_service_integration.this
}
```

[top](#index)