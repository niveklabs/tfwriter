# azurerm_frontdoor_firewall_policy

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
module "azurerm_frontdoor_firewall_policy" {
  source = "./modules/azurerm/r/azurerm_frontdoor_firewall_policy"

  # custom_block_response_body - (optional) is a type of string
  custom_block_response_body = null
  # custom_block_response_status_code - (optional) is a type of number
  custom_block_response_status_code = null
  # enabled - (optional) is a type of bool
  enabled = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # redirect_url - (optional) is a type of string
  redirect_url = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  custom_rule = [{
    action  = null
    enabled = null
    match_condition = [{
      match_values       = []
      match_variable     = null
      negation_condition = null
      operator           = null
      selector           = null
      transforms         = []
    }]
    name                           = null
    priority                       = null
    rate_limit_duration_in_minutes = null
    rate_limit_threshold           = null
    type                           = null
  }]

  managed_rule = [{
    exclusion = [{
      match_variable = null
      operator       = null
      selector       = null
    }]
    override = [{
      exclusion = [{
        match_variable = null
        operator       = null
        selector       = null
      }]
      rule = [{
        action  = null
        enabled = null
        exclusion = [{
          match_variable = null
          operator       = null
          selector       = null
        }]
        rule_id = null
      }]
      rule_group_name = null
    }]
    type    = null
    version = null
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
variable "custom_block_response_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_block_response_status_code" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "redirect_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "custom_rule" {
  description = "nested block: NestingList, min items: 0, max items: 100"
  type = set(object(
    {
      action  = string
      enabled = bool
      match_condition = list(object(
        {
          match_values       = list(string)
          match_variable     = string
          negation_condition = bool
          operator           = string
          selector           = string
          transforms         = list(string)
        }
      ))
      name                           = string
      priority                       = number
      rate_limit_duration_in_minutes = number
      rate_limit_threshold           = number
      type                           = string
    }
  ))
  default = []
}

variable "managed_rule" {
  description = "nested block: NestingList, min items: 0, max items: 100"
  type = set(object(
    {
      exclusion = list(object(
        {
          match_variable = string
          operator       = string
          selector       = string
        }
      ))
      override = list(object(
        {
          exclusion = list(object(
            {
              match_variable = string
              operator       = string
              selector       = string
            }
          ))
          rule = list(object(
            {
              action  = string
              enabled = bool
              exclusion = list(object(
                {
                  match_variable = string
                  operator       = string
                  selector       = string
                }
              ))
              rule_id = string
            }
          ))
          rule_group_name = string
        }
      ))
      type    = string
      version = string
    }
  ))
  default = []
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
resource "azurerm_frontdoor_firewall_policy" "this" {
  custom_block_response_body        = var.custom_block_response_body
  custom_block_response_status_code = var.custom_block_response_status_code
  enabled                           = var.enabled
  mode                              = var.mode
  name                              = var.name
  redirect_url                      = var.redirect_url
  resource_group_name               = var.resource_group_name
  tags                              = var.tags

  dynamic "custom_rule" {
    for_each = var.custom_rule
    content {
      action                         = custom_rule.value["action"]
      enabled                        = custom_rule.value["enabled"]
      name                           = custom_rule.value["name"]
      priority                       = custom_rule.value["priority"]
      rate_limit_duration_in_minutes = custom_rule.value["rate_limit_duration_in_minutes"]
      rate_limit_threshold           = custom_rule.value["rate_limit_threshold"]
      type                           = custom_rule.value["type"]

      dynamic "match_condition" {
        for_each = custom_rule.value.match_condition
        content {
          match_values       = match_condition.value["match_values"]
          match_variable     = match_condition.value["match_variable"]
          negation_condition = match_condition.value["negation_condition"]
          operator           = match_condition.value["operator"]
          selector           = match_condition.value["selector"]
          transforms         = match_condition.value["transforms"]
        }
      }

    }
  }

  dynamic "managed_rule" {
    for_each = var.managed_rule
    content {
      type    = managed_rule.value["type"]
      version = managed_rule.value["version"]

      dynamic "exclusion" {
        for_each = managed_rule.value.exclusion
        content {
          match_variable = exclusion.value["match_variable"]
          operator       = exclusion.value["operator"]
          selector       = exclusion.value["selector"]
        }
      }

      dynamic "override" {
        for_each = managed_rule.value.override
        content {
          rule_group_name = override.value["rule_group_name"]

          dynamic "exclusion" {
            for_each = override.value.exclusion
            content {
              match_variable = exclusion.value["match_variable"]
              operator       = exclusion.value["operator"]
              selector       = exclusion.value["selector"]
            }
          }

          dynamic "rule" {
            for_each = override.value.rule
            content {
              action  = rule.value["action"]
              enabled = rule.value["enabled"]
              rule_id = rule.value["rule_id"]

              dynamic "exclusion" {
                for_each = rule.value.exclusion
                content {
                  match_variable = exclusion.value["match_variable"]
                  operator       = exclusion.value["operator"]
                  selector       = exclusion.value["selector"]
                }
              }

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
output "frontend_endpoint_ids" {
  description = "returns a list of string"
  value       = azurerm_frontdoor_firewall_policy.this.frontend_endpoint_ids
}

output "id" {
  description = "returns a string"
  value       = azurerm_frontdoor_firewall_policy.this.id
}

output "location" {
  description = "returns a string"
  value       = azurerm_frontdoor_firewall_policy.this.location
}

output "this" {
  value = azurerm_frontdoor_firewall_policy.this
}
```

[top](#index)