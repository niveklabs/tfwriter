# azurerm_netapp_account

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
module "azurerm_netapp_account" {
  source = "./modules/azurerm/r/azurerm_netapp_account"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  active_directory = [{
    dns_servers         = []
    domain              = null
    organizational_unit = null
    password            = null
    smb_server_name     = null
    username            = null
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
variable "location" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "active_directory" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dns_servers         = list(string)
      domain              = string
      organizational_unit = string
      password            = string
      smb_server_name     = string
      username            = string
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
resource "azurerm_netapp_account" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "active_directory" {
    for_each = var.active_directory
    content {
      dns_servers         = active_directory.value["dns_servers"]
      domain              = active_directory.value["domain"]
      organizational_unit = active_directory.value["organizational_unit"]
      password            = active_directory.value["password"]
      smb_server_name     = active_directory.value["smb_server_name"]
      username            = active_directory.value["username"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_netapp_account.this.id
}

output "this" {
  value = azurerm_netapp_account.this
}
```

[top](#index)