# azurerm_mssql_firewall_rule

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
module "azurerm_mssql_firewall_rule" {
  source = "./modules/azurerm/r/azurerm_mssql_firewall_rule"

  # end_ip_address - (required) is a type of string
  end_ip_address = null
  # name - (required) is a type of string
  name = null
  # server_id - (required) is a type of string
  server_id = null
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
variable "end_ip_address" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "server_id" {
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
resource "azurerm_mssql_firewall_rule" "this" {
  # end_ip_address - (required) is a type of string
  end_ip_address = var.end_ip_address
  # name - (required) is a type of string
  name = var.name
  # server_id - (required) is a type of string
  server_id = var.server_id
  # start_ip_address - (required) is a type of string
  start_ip_address = var.start_ip_address

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
  value       = azurerm_mssql_firewall_rule.this.id
}

output "this" {
  value = azurerm_mssql_firewall_rule.this
}
```

[top](#index)