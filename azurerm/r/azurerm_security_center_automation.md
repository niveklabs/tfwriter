# azurerm_security_center_automation

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_security_center_automation" {
  source = [{
    event_source = null
    rule_set = [{
      rule = [{
        expected_value = null
        operator       = null
        property_path  = null
        property_type  = null
      }]
    }]
  }]

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scopes - (required) is a type of list of string
  scopes = []
  # tags - (optional) is a type of map of string
  tags = {}

  action = [{
    connection_string = null
    resource_id       = null
    trigger_url       = null
    type              = null
  }]


  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "scopes" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "action" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      connection_string = string
      resource_id       = string
      trigger_url       = string
      type              = string
    }
  ))
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      event_source = string
      rule_set = list(object(
        {
          rule = list(object(
            {
              expected_value = string
              operator       = string
              property_path  = string
              property_type  = string
            }
          ))
        }
      ))
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_security_center_automation" "this" {
  description         = var.description
  enabled             = var.enabled
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  scopes              = var.scopes
  tags                = var.tags

  dynamic "action" {
    for_each = var.action
    content {
      connection_string = action.value["connection_string"]
      resource_id       = action.value["resource_id"]
      trigger_url       = action.value["trigger_url"]
      type              = action.value["type"]
    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      event_source = source.value["event_source"]

      dynamic "rule_set" {
        for_each = source.value.rule_set
        content {

          dynamic "rule" {
            for_each = rule_set.value.rule
            content {
              expected_value = rule.value["expected_value"]
              operator       = rule.value["operator"]
              property_path  = rule.value["property_path"]
              property_type  = rule.value["property_type"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_security_center_automation.this.id
}

output "this" {
  value = azurerm_security_center_automation.this
}
```

[top](#index)