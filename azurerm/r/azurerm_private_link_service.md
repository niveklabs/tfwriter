# azurerm_private_link_service

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
module "azurerm_private_link_service" {
  source = "./modules/azurerm/r/azurerm_private_link_service"

  # auto_approval_subscription_ids - (optional) is a type of set of string
  auto_approval_subscription_ids = []
  # enable_proxy_protocol - (optional) is a type of bool
  enable_proxy_protocol = null
  # load_balancer_frontend_ip_configuration_ids - (required) is a type of set of string
  load_balancer_frontend_ip_configuration_ids = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # visibility_subscription_ids - (optional) is a type of set of string
  visibility_subscription_ids = []

  nat_ip_configuration = [{
    name                       = null
    primary                    = null
    private_ip_address         = null
    private_ip_address_version = null
    subnet_id                  = null
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
variable "auto_approval_subscription_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "enable_proxy_protocol" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_balancer_frontend_ip_configuration_ids" {
  description = "(required)"
  type        = set(string)
}

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

variable "visibility_subscription_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "nat_ip_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 8"
  type = set(object(
    {
      name                       = string
      primary                    = bool
      private_ip_address         = string
      private_ip_address_version = string
      subnet_id                  = string
    }
  ))
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
resource "azurerm_private_link_service" "this" {
  auto_approval_subscription_ids              = var.auto_approval_subscription_ids
  enable_proxy_protocol                       = var.enable_proxy_protocol
  load_balancer_frontend_ip_configuration_ids = var.load_balancer_frontend_ip_configuration_ids
  location                                    = var.location
  name                                        = var.name
  resource_group_name                         = var.resource_group_name
  tags                                        = var.tags
  visibility_subscription_ids                 = var.visibility_subscription_ids

  dynamic "nat_ip_configuration" {
    for_each = var.nat_ip_configuration
    content {
      name                       = nat_ip_configuration.value["name"]
      primary                    = nat_ip_configuration.value["primary"]
      private_ip_address         = nat_ip_configuration.value["private_ip_address"]
      private_ip_address_version = nat_ip_configuration.value["private_ip_address_version"]
      subnet_id                  = nat_ip_configuration.value["subnet_id"]
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
output "alias" {
  description = "returns a string"
  value       = azurerm_private_link_service.this.alias
}

output "id" {
  description = "returns a string"
  value       = azurerm_private_link_service.this.id
}

output "this" {
  value = azurerm_private_link_service.this
}
```

[top](#index)