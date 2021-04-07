# azurerm_web_application_firewall_policy

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
module "azurerm_web_application_firewall_policy" {
  source = "./modules/azurerm/r/azurerm_web_application_firewall_policy"

  # http_listener_ids - (optional) is a type of list of string
  http_listener_ids = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # path_based_rule_ids - (optional) is a type of list of string
  path_based_rule_ids = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  custom_rules = [{
    action = null
    match_conditions = [{
      match_values = []
      match_variables = [{
        selector      = null
        variable_name = null
      }]
      negation_condition = null
      operator           = null
      transforms         = []
    }]
    name      = null
    priority  = null
    rule_type = null
  }]

  managed_rules = [{
    exclusion = [{
      match_variable          = null
      selector                = null
      selector_match_operator = null
    }]
    managed_rule_set = [{
      rule_group_override = [{
        disabled_rules  = []
        rule_group_name = null
      }]
      type    = null
      version = null
    }]
  }]

  policy_settings = [{
    enabled                     = null
    file_upload_limit_in_mb     = null
    max_request_body_size_in_kb = null
    mode                        = null
    request_body_check          = null
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
variable "http_listener_ids" {
  description = "(optional)"
  type        = list(string)
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

variable "path_based_rule_ids" {
  description = "(optional)"
  type        = list(string)
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

variable "custom_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      match_conditions = list(object(
        {
          match_values = list(string)
          match_variables = list(object(
            {
              selector      = string
              variable_name = string
            }
          ))
          negation_condition = bool
          operator           = string
          transforms         = set(string)
        }
      ))
      name      = string
      priority  = number
      rule_type = string
    }
  ))
  default = []
}

variable "managed_rules" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      exclusion = list(object(
        {
          match_variable          = string
          selector                = string
          selector_match_operator = string
        }
      ))
      managed_rule_set = list(object(
        {
          rule_group_override = list(object(
            {
              disabled_rules  = list(string)
              rule_group_name = string
            }
          ))
          type    = string
          version = string
        }
      ))
    }
  ))
}

variable "policy_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled                     = bool
      file_upload_limit_in_mb     = number
      max_request_body_size_in_kb = number
      mode                        = string
      request_body_check          = bool
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
resource "azurerm_web_application_firewall_policy" "this" {
  # http_listener_ids - (optional) is a type of list of string
  http_listener_ids = var.http_listener_ids
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # path_based_rule_ids - (optional) is a type of list of string
  path_based_rule_ids = var.path_based_rule_ids
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "custom_rules" {
    for_each = var.custom_rules
    content {
      # action - (required) is a type of string
      action = custom_rules.value["action"]
      # name - (optional) is a type of string
      name = custom_rules.value["name"]
      # priority - (required) is a type of number
      priority = custom_rules.value["priority"]
      # rule_type - (required) is a type of string
      rule_type = custom_rules.value["rule_type"]

      dynamic "match_conditions" {
        for_each = custom_rules.value.match_conditions
        content {
          # match_values - (required) is a type of list of string
          match_values = match_conditions.value["match_values"]
          # negation_condition - (optional) is a type of bool
          negation_condition = match_conditions.value["negation_condition"]
          # operator - (required) is a type of string
          operator = match_conditions.value["operator"]
          # transforms - (optional) is a type of set of string
          transforms = match_conditions.value["transforms"]

          dynamic "match_variables" {
            for_each = match_conditions.value.match_variables
            content {
              # selector - (optional) is a type of string
              selector = match_variables.value["selector"]
              # variable_name - (required) is a type of string
              variable_name = match_variables.value["variable_name"]
            }
          }

        }
      }

    }
  }

  dynamic "managed_rules" {
    for_each = var.managed_rules
    content {

      dynamic "exclusion" {
        for_each = managed_rules.value.exclusion
        content {
          # match_variable - (required) is a type of string
          match_variable = exclusion.value["match_variable"]
          # selector - (required) is a type of string
          selector = exclusion.value["selector"]
          # selector_match_operator - (required) is a type of string
          selector_match_operator = exclusion.value["selector_match_operator"]
        }
      }

      dynamic "managed_rule_set" {
        for_each = managed_rules.value.managed_rule_set
        content {
          # type - (optional) is a type of string
          type = managed_rule_set.value["type"]
          # version - (required) is a type of string
          version = managed_rule_set.value["version"]

          dynamic "rule_group_override" {
            for_each = managed_rule_set.value.rule_group_override
            content {
              # disabled_rules - (required) is a type of list of string
              disabled_rules = rule_group_override.value["disabled_rules"]
              # rule_group_name - (required) is a type of string
              rule_group_name = rule_group_override.value["rule_group_name"]
            }
          }

        }
      }

    }
  }

  dynamic "policy_settings" {
    for_each = var.policy_settings
    content {
      # enabled - (optional) is a type of bool
      enabled = policy_settings.value["enabled"]
      # file_upload_limit_in_mb - (optional) is a type of number
      file_upload_limit_in_mb = policy_settings.value["file_upload_limit_in_mb"]
      # max_request_body_size_in_kb - (optional) is a type of number
      max_request_body_size_in_kb = policy_settings.value["max_request_body_size_in_kb"]
      # mode - (optional) is a type of string
      mode = policy_settings.value["mode"]
      # request_body_check - (optional) is a type of bool
      request_body_check = policy_settings.value["request_body_check"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = azurerm_web_application_firewall_policy.this.id
}

output "this" {
  value = azurerm_web_application_firewall_policy.this
}
```

[top](#index)