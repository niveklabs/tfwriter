# azurerm_traffic_manager_profile

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_traffic_manager_profile" {
  source = "./modules/azurerm/d/azurerm_traffic_manager_profile"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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
data "azurerm_traffic_manager_profile" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

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
output "dns_config" {
  description = "returns a list of object"
  value       = data.azurerm_traffic_manager_profile.this.dns_config
}

output "fqdn" {
  description = "returns a string"
  value       = data.azurerm_traffic_manager_profile.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_traffic_manager_profile.this.id
}

output "monitor_config" {
  description = "returns a list of object"
  value       = data.azurerm_traffic_manager_profile.this.monitor_config
}

output "profile_status" {
  description = "returns a string"
  value       = data.azurerm_traffic_manager_profile.this.profile_status
}

output "traffic_routing_method" {
  description = "returns a string"
  value       = data.azurerm_traffic_manager_profile.this.traffic_routing_method
}

output "this" {
  value = azurerm_traffic_manager_profile.this
}
```

[top](#index)