# azurerm_traffic_manager_endpoint

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
module "azurerm_traffic_manager_endpoint" {
  source = "./modules/azurerm/r/azurerm_traffic_manager_endpoint"

  # endpoint_location - (optional) is a type of string
  endpoint_location = null
  # endpoint_status - (optional) is a type of string
  endpoint_status = null
  # geo_mappings - (optional) is a type of list of string
  geo_mappings = []
  # min_child_endpoints - (optional) is a type of number
  min_child_endpoints = null
  # name - (required) is a type of string
  name = null
  # priority - (optional) is a type of number
  priority = null
  # profile_name - (required) is a type of string
  profile_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # target - (optional) is a type of string
  target = null
  # target_resource_id - (optional) is a type of string
  target_resource_id = null
  # type - (required) is a type of string
  type = null
  # weight - (optional) is a type of number
  weight = null

  custom_header = [{
    name  = null
    value = null
  }]

  subnet = [{
    first = null
    last  = null
    scope = null
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
variable "endpoint_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geo_mappings" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "min_child_endpoints" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "profile_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "custom_header" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "subnet" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      first = string
      last  = string
      scope = number
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
resource "azurerm_traffic_manager_endpoint" "this" {
  endpoint_location   = var.endpoint_location
  endpoint_status     = var.endpoint_status
  geo_mappings        = var.geo_mappings
  min_child_endpoints = var.min_child_endpoints
  name                = var.name
  priority            = var.priority
  profile_name        = var.profile_name
  resource_group_name = var.resource_group_name
  target              = var.target
  target_resource_id  = var.target_resource_id
  type                = var.type
  weight              = var.weight

  dynamic "custom_header" {
    for_each = var.custom_header
    content {
      name  = custom_header.value["name"]
      value = custom_header.value["value"]
    }
  }

  dynamic "subnet" {
    for_each = var.subnet
    content {
      first = subnet.value["first"]
      last  = subnet.value["last"]
      scope = subnet.value["scope"]
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
output "endpoint_location" {
  description = "returns a string"
  value       = azurerm_traffic_manager_endpoint.this.endpoint_location
}

output "endpoint_monitor_status" {
  description = "returns a string"
  value       = azurerm_traffic_manager_endpoint.this.endpoint_monitor_status
}

output "endpoint_status" {
  description = "returns a string"
  value       = azurerm_traffic_manager_endpoint.this.endpoint_status
}

output "id" {
  description = "returns a string"
  value       = azurerm_traffic_manager_endpoint.this.id
}

output "priority" {
  description = "returns a number"
  value       = azurerm_traffic_manager_endpoint.this.priority
}

output "target" {
  description = "returns a string"
  value       = azurerm_traffic_manager_endpoint.this.target
}

output "weight" {
  description = "returns a number"
  value       = azurerm_traffic_manager_endpoint.this.weight
}

output "this" {
  value = azurerm_traffic_manager_endpoint.this
}
```

[top](#index)