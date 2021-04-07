# azurerm_lb

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
module "azurerm_lb" {
  source = "./modules/azurerm/r/azurerm_lb"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (optional) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}

  frontend_ip_configuration = [{
    id                            = null
    inbound_nat_rules             = []
    load_balancer_rules           = []
    name                          = null
    outbound_rules                = []
    private_ip_address            = null
    private_ip_address_allocation = null
    private_ip_address_version    = null
    public_ip_address_id          = null
    public_ip_prefix_id           = null
    subnet_id                     = null
    zones                         = []
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

variable "sku" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "frontend_ip_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id                            = string
      inbound_nat_rules             = set(string)
      load_balancer_rules           = set(string)
      name                          = string
      outbound_rules                = set(string)
      private_ip_address            = string
      private_ip_address_allocation = string
      private_ip_address_version    = string
      public_ip_address_id          = string
      public_ip_prefix_id           = string
      subnet_id                     = string
      zones                         = list(string)
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
resource "azurerm_lb" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku - (optional) is a type of string
  sku = var.sku
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "frontend_ip_configuration" {
    for_each = var.frontend_ip_configuration
    content {
      # name - (required) is a type of string
      name = frontend_ip_configuration.value["name"]
      # private_ip_address - (optional) is a type of string
      private_ip_address = frontend_ip_configuration.value["private_ip_address"]
      # private_ip_address_allocation - (optional) is a type of string
      private_ip_address_allocation = frontend_ip_configuration.value["private_ip_address_allocation"]
      # private_ip_address_version - (optional) is a type of string
      private_ip_address_version = frontend_ip_configuration.value["private_ip_address_version"]
      # public_ip_address_id - (optional) is a type of string
      public_ip_address_id = frontend_ip_configuration.value["public_ip_address_id"]
      # public_ip_prefix_id - (optional) is a type of string
      public_ip_prefix_id = frontend_ip_configuration.value["public_ip_prefix_id"]
      # subnet_id - (optional) is a type of string
      subnet_id = frontend_ip_configuration.value["subnet_id"]
      # zones - (optional) is a type of list of string
      zones = frontend_ip_configuration.value["zones"]
    }
  }

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
  value       = azurerm_lb.this.id
}

output "private_ip_address" {
  description = "returns a string"
  value       = azurerm_lb.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_lb.this.private_ip_addresses
}

output "this" {
  value = azurerm_lb.this
}
```

[top](#index)