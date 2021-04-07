# pagerduty_extension

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
module "pagerduty_extension" {
  source = "./modules/pagerduty/r/pagerduty_extension"

  # config - (optional) is a type of string
  config = null
  # endpoint_url - (optional) is a type of string
  endpoint_url = null
  # extension_objects - (required) is a type of set of string
  extension_objects = []
  # extension_schema - (required) is a type of string
  extension_schema = null
  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extension_objects" {
  description = "(required)"
  type        = set(string)
}

variable "extension_schema" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_extension" "this" {
  config            = var.config
  endpoint_url      = var.endpoint_url
  extension_objects = var.extension_objects
  extension_schema  = var.extension_schema
  name              = var.name
  type              = var.type
}
```

[top](#index)

### Outputs

```terraform
output "html_url" {
  description = "returns a string"
  value       = pagerduty_extension.this.html_url
}

output "id" {
  description = "returns a string"
  value       = pagerduty_extension.this.id
}

output "name" {
  description = "returns a string"
  value       = pagerduty_extension.this.name
}

output "type" {
  description = "returns a string"
  value       = pagerduty_extension.this.type
}

output "this" {
  value = pagerduty_extension.this
}
```

[top](#index)