# azurerm_firewall

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
module "azurerm_firewall" {
  source = "./modules/azurerm/r/azurerm_firewall"

  # dns_servers - (optional) is a type of list of string
  dns_servers = []
  # firewall_policy_id - (optional) is a type of string
  firewall_policy_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (optional) is a type of string
  sku_name = null
  # sku_tier - (optional) is a type of string
  sku_tier = null
  # tags - (optional) is a type of map of string
  tags = {}
  # threat_intel_mode - (optional) is a type of string
  threat_intel_mode = null
  # zones - (optional) is a type of list of string
  zones = []

  ip_configuration = [{
    name                 = null
    private_ip_address   = null
    public_ip_address_id = null
    subnet_id            = null
  }]

  management_ip_configuration = [{
    name                 = null
    private_ip_address   = null
    public_ip_address_id = null
    subnet_id            = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  virtual_hub = [{
    private_ip_address  = null
    public_ip_addresses = []
    public_ip_count     = null
    virtual_hub_id      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dns_servers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "firewall_policy_id" {
  description = "(optional)"
  type        = string
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sku_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "threat_intel_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ip_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name                 = string
      private_ip_address   = string
      public_ip_address_id = string
      subnet_id            = string
    }
  ))
  default = []
}

variable "management_ip_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name                 = string
      private_ip_address   = string
      public_ip_address_id = string
      subnet_id            = string
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

variable "virtual_hub" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      private_ip_address  = string
      public_ip_addresses = list(string)
      public_ip_count     = number
      virtual_hub_id      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_firewall" "this" {
  dns_servers         = var.dns_servers
  firewall_policy_id  = var.firewall_policy_id
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  sku_name            = var.sku_name
  sku_tier            = var.sku_tier
  tags                = var.tags
  threat_intel_mode   = var.threat_intel_mode
  zones               = var.zones

  dynamic "ip_configuration" {
    for_each = var.ip_configuration
    content {
      name                 = ip_configuration.value["name"]
      public_ip_address_id = ip_configuration.value["public_ip_address_id"]
      subnet_id            = ip_configuration.value["subnet_id"]
    }
  }

  dynamic "management_ip_configuration" {
    for_each = var.management_ip_configuration
    content {
      name                 = management_ip_configuration.value["name"]
      public_ip_address_id = management_ip_configuration.value["public_ip_address_id"]
      subnet_id            = management_ip_configuration.value["subnet_id"]
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

  dynamic "virtual_hub" {
    for_each = var.virtual_hub
    content {
      public_ip_count = virtual_hub.value["public_ip_count"]
      virtual_hub_id  = virtual_hub.value["virtual_hub_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_firewall.this.id
}

output "sku_name" {
  description = "returns a string"
  value       = azurerm_firewall.this.sku_name
}

output "sku_tier" {
  description = "returns a string"
  value       = azurerm_firewall.this.sku_tier
}

output "this" {
  value = azurerm_firewall.this
}
```

[top](#index)