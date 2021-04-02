# azurerm_nat_gateway

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
module "azurerm_nat_gateway" {
  source = "./modules/azurerm/r/azurerm_nat_gateway"

  # idle_timeout_in_minutes - (optional) is a type of number
  idle_timeout_in_minutes = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # public_ip_address_ids - (optional) is a type of set of string
  public_ip_address_ids = []
  # public_ip_prefix_ids - (optional) is a type of set of string
  public_ip_prefix_ids = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (optional) is a type of string
  sku_name = null
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
variable "idle_timeout_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_ip_address_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "public_ip_prefix_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_nat_gateway" "this" {
  idle_timeout_in_minutes = var.idle_timeout_in_minutes
  location                = var.location
  name                    = var.name
  public_ip_address_ids   = var.public_ip_address_ids
  public_ip_prefix_ids    = var.public_ip_prefix_ids
  resource_group_name     = var.resource_group_name
  sku_name                = var.sku_name
  tags                    = var.tags
  zones                   = var.zones

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
  value       = azurerm_nat_gateway.this.id
}

output "public_ip_address_ids" {
  description = "returns a set of string"
  value       = azurerm_nat_gateway.this.public_ip_address_ids
}

output "resource_guid" {
  description = "returns a string"
  value       = azurerm_nat_gateway.this.resource_guid
}

output "this" {
  value = azurerm_nat_gateway.this
}
```

[top](#index)