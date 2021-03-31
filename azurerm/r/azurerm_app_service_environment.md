# azurerm_app_service_environment

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
module "azurerm_app_service_environment" {
  source = "./modules/azurerm/r/azurerm_app_service_environment"

  # allowed_user_ip_cidrs - (optional) is a type of set of string
  allowed_user_ip_cidrs = []
  # front_end_scale_factor - (optional) is a type of number
  front_end_scale_factor = null
  # internal_load_balancing_mode - (optional) is a type of string
  internal_load_balancing_mode = null
  # name - (required) is a type of string
  name = null
  # pricing_tier - (optional) is a type of string
  pricing_tier = null
  # resource_group_name - (optional) is a type of string
  resource_group_name = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_whitelisted_ip_ranges - (optional) is a type of set of string
  user_whitelisted_ip_ranges = []

  cluster_setting = [{
    name  = null
    value = null
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
variable "allowed_user_ip_cidrs" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "front_end_scale_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internal_load_balancing_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pricing_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_whitelisted_ip_ranges" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cluster_setting" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
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
resource "azurerm_app_service_environment" "this" {
  allowed_user_ip_cidrs        = var.allowed_user_ip_cidrs
  front_end_scale_factor       = var.front_end_scale_factor
  internal_load_balancing_mode = var.internal_load_balancing_mode
  name                         = var.name
  pricing_tier                 = var.pricing_tier
  resource_group_name          = var.resource_group_name
  subnet_id                    = var.subnet_id
  tags                         = var.tags
  user_whitelisted_ip_ranges   = var.user_whitelisted_ip_ranges

  dynamic "cluster_setting" {
    for_each = var.cluster_setting
    content {
      name  = cluster_setting.value["name"]
      value = cluster_setting.value["value"]
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
output "allowed_user_ip_cidrs" {
  description = "returns a set of string"
  value       = azurerm_app_service_environment.this.allowed_user_ip_cidrs
}

output "id" {
  description = "returns a string"
  value       = azurerm_app_service_environment.this.id
}

output "location" {
  description = "returns a string"
  value       = azurerm_app_service_environment.this.location
}

output "resource_group_name" {
  description = "returns a string"
  value       = azurerm_app_service_environment.this.resource_group_name
}

output "user_whitelisted_ip_ranges" {
  description = "returns a set of string"
  value       = azurerm_app_service_environment.this.user_whitelisted_ip_ranges
}

output "this" {
  value = azurerm_app_service_environment.this
}
```

[top](#index)