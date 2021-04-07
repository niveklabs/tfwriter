# onelogin_user_mappings

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
module "onelogin_user_mappings" {
  source = "./modules/onelogin/r/onelogin_user_mappings"

  # enabled - (optional) is a type of bool
  enabled = null
  # match - (required) is a type of string
  match = null
  # name - (required) is a type of string
  name = null
  # position - (required) is a type of number
  position = null

  actions = [{
    action = null
    value  = []
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
  description = "(required)"
  type        = number
}

variable "actions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      value  = list(string)
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
resource "onelogin_user_mappings" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # match - (required) is a type of string
  match = var.match
  # name - (required) is a type of string
  name = var.name
  # position - (required) is a type of number
  position = var.position

  dynamic "actions" {
    for_each = var.actions
    content {
      # action - (required) is a type of string
      action = actions.value["action"]
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
  value       = onelogin_user_mappings.this.id
}

output "this" {
  value = onelogin_user_mappings.this
}
```

[top](#index)