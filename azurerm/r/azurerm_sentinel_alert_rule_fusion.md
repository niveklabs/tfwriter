# azurerm_sentinel_alert_rule_fusion

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_sentinel_alert_rule_fusion" {
  source = "./modules/azurerm/r/azurerm_sentinel_alert_rule_fusion"

  # alert_rule_template_guid - (required) is a type of string
  alert_rule_template_guid = null
  # enabled - (optional) is a type of bool
  enabled = null
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null

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
variable "alert_rule_template_guid" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "log_analytics_workspace_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "azurerm_sentinel_alert_rule_fusion" "this" {
  alert_rule_template_guid   = var.alert_rule_template_guid
  enabled                    = var.enabled
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name

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
  value       = azurerm_sentinel_alert_rule_fusion.this.id
}

output "this" {
  value = azurerm_sentinel_alert_rule_fusion.this
}
```

[top](#index)