# onelogin_app_rules

[back](../onelogin.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    onelogin = ">= 0.1.12"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "onelogin_app_rules" {
  source = "./modules/onelogin/r/onelogin_app_rules"

  # app_id - (required) is a type of string
  app_id = null
  # enabled - (optional) is a type of bool
  enabled = null
  # match - (required) is a type of string
  match = null
  # name - (required) is a type of string
  name = null
  # position - (optional) is a type of number
  position = null

  actions = [{
    action     = null
    expression = null
    value      = []
  }]

  conditions = [{
    operator = null
    source   = null
    value    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "match" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "position" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "actions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action     = string
      expression = string
      value      = list(string)
    }
  ))
  default = []
}

variable "conditions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      operator = string
      source   = string
      value    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_app_rules" "this" {
  # app_id - (required) is a type of string
  app_id = var.app_id
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # match - (required) is a type of string
  match = var.match
  # name - (required) is a type of string
  name = var.name
  # position - (optional) is a type of number
  position = var.position

  dynamic "actions" {
    for_each = var.actions
    content {
      # action - (required) is a type of string
      action = actions.value["action"]
      # expression - (optional) is a type of string
      expression = actions.value["expression"]
      # value - (required) is a type of list of string
      value = actions.value["value"]
    }
  }

  dynamic "conditions" {
    for_each = var.conditions
    content {
      # operator - (required) is a type of string
      operator = conditions.value["operator"]
      # source - (required) is a type of string
      source = conditions.value["source"]
      # value - (required) is a type of string
      value = conditions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = onelogin_app_rules.this.id
}

output "position" {
  description = "returns a number"
  value       = onelogin_app_rules.this.position
}

output "this" {
  value = onelogin_app_rules.this
}
```

[top](#index)