# azurerm_mssql_virtual_network_rule

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
module "azurerm_mssql_virtual_network_rule" {
  source = "./modules/azurerm/r/azurerm_mssql_virtual_network_rule"

  # ignore_missing_vnet_service_endpoint - (optional) is a type of bool
  ignore_missing_vnet_service_endpoint = null
  # name - (required) is a type of string
  name = null
  # server_id - (required) is a type of string
  server_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null

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
variable "ignore_missing_vnet_service_endpoint" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "server_id" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
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
resource "azurerm_mssql_virtual_network_rule" "this" {
  ignore_missing_vnet_service_endpoint = var.ignore_missing_vnet_service_endpoint
  name                                 = var.name
  server_id                            = var.server_id
  subnet_id                            = var.subnet_id

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
  value       = azurerm_mssql_virtual_network_rule.this.id
}

output "this" {
  value = azurerm_mssql_virtual_network_rule.this
}
```

[top](#index)