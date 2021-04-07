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
    akamai = ">= 1.5.0"
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

  rule_errors = [{
    behavior_name  = null
    detail         = null
    error_location = null
    instance       = null
    status_code    = null
    title          = null
    type           = null
  }]

  rule_warnings = [{
    behavior_name  = null
    detail         = null
    error_location = null
    instance       = null
    status_code    = null
    title          = null
    type           = null
  }]

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

variable "rule_errors" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      behavior_name  = string
      detail         = string
      error_location = string
      instance       = string
      status_code    = number
      title          = string
      type           = string
    }
  ))
  default = []
}

variable "rule_warnings" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      behavior_name  = string
      detail         = string
      error_location = string
      instance       = string
      status_code    = number
      title          = string
      type           = string
    }
  ))
  default = []
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
  # activation_id - (optional) is a type of string
  activation_id = var.activation_id
  # contact - (required) is a type of set of string
  contact = var.contact
  # network - (optional) is a type of string
  network = var.network
  # property - (optional) is a type of string
  property = var.property
  # property_id - (optional) is a type of string
  property_id = var.property_id
  # version - (required) is a type of number
  version = var.version

  dynamic "rule_errors" {
    for_each = var.rule_errors
    content {
      # behavior_name - (optional) is a type of string
      behavior_name = rule_errors.value["behavior_name"]
      # detail - (optional) is a type of string
      detail = rule_errors.value["detail"]
      # error_location - (optional) is a type of string
      error_location = rule_errors.value["error_location"]
      # instance - (optional) is a type of string
      instance = rule_errors.value["instance"]
      # status_code - (optional) is a type of number
      status_code = rule_errors.value["status_code"]
      # title - (optional) is a type of string
      title = rule_errors.value["title"]
      # type - (optional) is a type of string
      type = rule_errors.value["type"]
    }
  }

  dynamic "rule_warnings" {
    for_each = var.rule_warnings
    content {
      # behavior_name - (optional) is a type of string
      behavior_name = rule_warnings.value["behavior_name"]
      # detail - (optional) is a type of string
      detail = rule_warnings.value["detail"]
      # error_location - (optional) is a type of string
      error_location = rule_warnings.value["error_location"]
      # instance - (optional) is a type of string
      instance = rule_warnings.value["instance"]
      # status_code - (optional) is a type of number
      status_code = rule_warnings.value["status_code"]
      # title - (optional) is a type of string
      title = rule_warnings.value["title"]
      # type - (optional) is a type of string
      type = rule_warnings.value["type"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
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