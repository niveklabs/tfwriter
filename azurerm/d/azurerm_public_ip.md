# azurerm_public_ip

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_public_ip" {
  source = "./modules/azurerm/d/azurerm_public_ip"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_public_ip" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags
  zones               = var.zones

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allocation_method" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.allocation_method
}

output "domain_name_label" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.domain_name_label
}

output "fqdn" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.id
}

output "idle_timeout_in_minutes" {
  description = "returns a number"
  value       = data.azurerm_public_ip.this.idle_timeout_in_minutes
}

output "ip_address" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.ip_address
}

output "ip_version" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.ip_version
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.location
}

output "reverse_fqdn" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.reverse_fqdn
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_public_ip.this.sku
}

output "zones" {
  description = "returns a list of string"
  value       = data.azurerm_public_ip.this.zones
}

output "this" {
  value = azurerm_public_ip.this
}
```

[top](#index)