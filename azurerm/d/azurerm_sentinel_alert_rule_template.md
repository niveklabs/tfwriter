# azurerm_sentinel_alert_rule_template

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_sentinel_alert_rule_template" {
  source = "./modules/azurerm/d/azurerm_sentinel_alert_rule_template"

  # display_name - (optional) is a type of string
  display_name = null
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (optional) is a type of string
  name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_analytics_workspace_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_sentinel_alert_rule_template" "this" {
  display_name               = var.display_name
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.azurerm_sentinel_alert_rule_template.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_sentinel_alert_rule_template.this.id
}

output "name" {
  description = "returns a string"
  value       = data.azurerm_sentinel_alert_rule_template.this.name
}

output "scheduled_template" {
  description = "returns a list of object"
  value       = data.azurerm_sentinel_alert_rule_template.this.scheduled_template
}

output "security_incident_template" {
  description = "returns a list of object"
  value       = data.azurerm_sentinel_alert_rule_template.this.security_incident_template
}

output "this" {
  value = azurerm_sentinel_alert_rule_template.this
}
```

[top](#index)