# azurerm_sentinel_alert_rule_ms_security_incident

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_sentinel_alert_rule_ms_security_incident" {
  source = "./modules/azurerm/r/azurerm_sentinel_alert_rule_ms_security_incident"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # display_name_filter - (optional) is a type of set of string
  display_name_filter = []
  # enabled - (optional) is a type of bool
  enabled = null
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null
  # product_filter - (required) is a type of string
  product_filter = null
  # severity_filter - (required) is a type of set of string
  severity_filter = []
  # text_whitelist - (optional) is a type of set of string
  text_whitelist = []

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

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "display_name_filter" {
  description = "(optional)"
  type        = set(string)
  default     = null
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

variable "product_filter" {
  description = "(required)"
  type        = string
}

variable "severity_filter" {
  description = "(required)"
  type        = set(string)
}

variable "text_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
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
resource "azurerm_sentinel_alert_rule_ms_security_incident" "this" {
  description                = var.description
  display_name               = var.display_name
  display_name_filter        = var.display_name_filter
  enabled                    = var.enabled
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name
  product_filter             = var.product_filter
  severity_filter            = var.severity_filter
  text_whitelist             = var.text_whitelist

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
output "display_name_filter" {
  description = "returns a set of string"
  value       = azurerm_sentinel_alert_rule_ms_security_incident.this.display_name_filter
}

output "id" {
  description = "returns a string"
  value       = azurerm_sentinel_alert_rule_ms_security_incident.this.id
}

output "text_whitelist" {
  description = "returns a set of string"
  value       = azurerm_sentinel_alert_rule_ms_security_incident.this.text_whitelist
}

output "this" {
  value = azurerm_sentinel_alert_rule_ms_security_incident.this
}
```

[top](#index)