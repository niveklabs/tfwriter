# azurerm_nat_gateway

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
module "azurerm_nat_gateway" {
  source = "./modules/azurerm/d/azurerm_nat_gateway"

  # name - (required) is a type of string
  name = null
  # public_ip_address_ids - (optional) is a type of list of string
  public_ip_address_ids = []
  # public_ip_prefix_ids - (optional) is a type of list of string
  public_ip_prefix_ids = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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

variable "public_ip_address_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "public_ip_prefix_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
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
data "azurerm_nat_gateway" "this" {
  name                  = var.name
  public_ip_address_ids = var.public_ip_address_ids
  public_ip_prefix_ids  = var.public_ip_prefix_ids
  resource_group_name   = var.resource_group_name

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_nat_gateway.this.id
}

output "idle_timeout_in_minutes" {
  description = "returns a number"
  value       = data.azurerm_nat_gateway.this.idle_timeout_in_minutes
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_nat_gateway.this.location
}

output "public_ip_address_ids" {
  description = "returns a list of string"
  value       = data.azurerm_nat_gateway.this.public_ip_address_ids
}

output "public_ip_prefix_ids" {
  description = "returns a list of string"
  value       = data.azurerm_nat_gateway.this.public_ip_prefix_ids
}

output "resource_guid" {
  description = "returns a string"
  value       = data.azurerm_nat_gateway.this.resource_guid
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_nat_gateway.this.sku_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_nat_gateway.this.tags
}

output "zones" {
  description = "returns a list of string"
  value       = data.azurerm_nat_gateway.this.zones
}

output "this" {
  value = azurerm_nat_gateway.this
}
```

[top](#index)