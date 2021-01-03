# azurerm_public_ip

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_public_ip" {
  source = "./modules/azurerm/r/azurerm_public_ip"

  # allocation_method - (required) is a type of string
  allocation_method = null
  # domain_name_label - (optional) is a type of string
  domain_name_label = null
  # idle_timeout_in_minutes - (optional) is a type of number
  idle_timeout_in_minutes = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # public_ip_prefix_id - (optional) is a type of string
  public_ip_prefix_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # reverse_fqdn - (optional) is a type of string
  reverse_fqdn = null
  # sku - (optional) is a type of string
  sku = null
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
variable "allocation_method" {
  description = "(required)"
  type        = string
}

variable "domain_name_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idle_timeout_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_version" {
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

variable "public_ip_prefix_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "reverse_fqdn" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_public_ip" "this" {
  allocation_method       = var.allocation_method
  domain_name_label       = var.domain_name_label
  idle_timeout_in_minutes = var.idle_timeout_in_minutes
  ip_version              = var.ip_version
  location                = var.location
  name                    = var.name
  public_ip_prefix_id     = var.public_ip_prefix_id
  resource_group_name     = var.resource_group_name
  reverse_fqdn            = var.reverse_fqdn
  sku                     = var.sku
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
output "fqdn" {
  description = "returns a string"
  value       = azurerm_public_ip.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_public_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = azurerm_public_ip.this.ip_address
}

output "this" {
  value = azurerm_public_ip.this
}
```

[top](#index)