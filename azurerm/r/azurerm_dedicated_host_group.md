# azurerm_dedicated_host_group

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
module "azurerm_dedicated_host_group" {
  source = "./modules/azurerm/r/azurerm_dedicated_host_group"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # platform_fault_domain_count - (required) is a type of number
  platform_fault_domain_count = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

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

variable "platform_fault_domain_count" {
  description = "(required)"
  type        = number
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

variable "zones" {
  description = "(optional)"
  type        = list(string)
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
resource "azurerm_dedicated_host_group" "this" {
  location                    = var.location
  name                        = var.name
  platform_fault_domain_count = var.platform_fault_domain_count
  resource_group_name         = var.resource_group_name
  tags                        = var.tags
  zones                       = var.zones

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
  value       = azurerm_dedicated_host_group.this.id
}

output "this" {
  value = azurerm_dedicated_host_group.this
}
```

[top](#index)