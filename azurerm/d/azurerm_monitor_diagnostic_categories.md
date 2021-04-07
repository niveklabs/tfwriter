# azurerm_monitor_diagnostic_categories

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
module "azurerm_monitor_diagnostic_categories" {
  source = "./modules/azurerm/d/azurerm_monitor_diagnostic_categories"

  # resource_id - (required) is a type of string
  resource_id = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
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
data "azurerm_monitor_diagnostic_categories" "this" {
  # resource_id - (required) is a type of string
  resource_id = var.resource_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
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
  value       = data.azurerm_monitor_diagnostic_categories.this.id
}

output "logs" {
  description = "returns a set of string"
  value       = data.azurerm_monitor_diagnostic_categories.this.logs
}

output "metrics" {
  description = "returns a set of string"
  value       = data.azurerm_monitor_diagnostic_categories.this.metrics
}

output "this" {
  value = azurerm_monitor_diagnostic_categories.this
}
```

[top](#index)