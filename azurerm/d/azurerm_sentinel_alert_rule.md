# azurerm_sentinel_alert_rule

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_sentinel_alert_rule" {
  source = "./modules/azurerm/d/azurerm_sentinel_alert_rule"

  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_sentinel_alert_rule" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.azurerm_sentinel_alert_rule.this.id
}

output "this" {
  value = azurerm_sentinel_alert_rule.this
}
```

[top](#index)