# azurerm_data_lake_store_firewall_rule

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
module "azurerm_data_lake_store_firewall_rule" {
  source = "./modules/azurerm/r/azurerm_data_lake_store_firewall_rule"

  # account_name - (required) is a type of string
  account_name = null
  # end_ip_address - (required) is a type of string
  end_ip_address = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # start_ip_address - (required) is a type of string
  start_ip_address = null

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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "end_ip_address" {
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

variable "start_ip_address" {
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
resource "azurerm_data_lake_store_firewall_rule" "this" {
  account_name        = var.account_name
  end_ip_address      = var.end_ip_address
  name                = var.name
  resource_group_name = var.resource_group_name
  start_ip_address    = var.start_ip_address

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
  value       = azurerm_data_lake_store_firewall_rule.this.id
}

output "this" {
  value = azurerm_data_lake_store_firewall_rule.this
}
```

[top](#index)