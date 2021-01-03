# akamai_property_activation

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_property_activation" {
  source = "./modules/akamai/r/akamai_property_activation"

  # activation_id - (optional) is a type of string
  activation_id = null
  # contact - (required) is a type of set of string
  contact = []
  # network - (optional) is a type of string
  network = null
  # property - (optional) is a type of string
  property = null
  # property_id - (optional) is a type of string
  property_id = null
  # version - (required) is a type of number
  version = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "activation_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contact" {
  description = "(required)"
  type        = set(string)
}

variable "network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "property" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "property_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(required)"
  type        = number
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_property_activation" "this" {
  activation_id = var.activation_id
  contact       = var.contact
  network       = var.network
  property      = var.property
  property_id   = var.property_id
  version       = var.version

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "activation_id" {
  description = "returns a string"
  value       = akamai_property_activation.this.activation_id
}

output "errors" {
  description = "returns a string"
  value       = akamai_property_activation.this.errors
}

output "id" {
  description = "returns a string"
  value       = akamai_property_activation.this.id
}

output "property" {
  description = "returns a string"
  value       = akamai_property_activation.this.property
}

output "property_id" {
  description = "returns a string"
  value       = akamai_property_activation.this.property_id
}

output "status" {
  description = "returns a string"
  value       = akamai_property_activation.this.status
}

output "warnings" {
  description = "returns a string"
  value       = akamai_property_activation.this.warnings
}

output "this" {
  value = akamai_property_activation.this
}
```

[top](#index)