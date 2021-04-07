# azurerm_app_service_plan

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
module "azurerm_app_service_plan" {
  source = "./modules/azurerm/r/azurerm_app_service_plan"

  # app_service_environment_id - (optional) is a type of string
  app_service_environment_id = null
  # is_xenon - (optional) is a type of bool
  is_xenon = null
  # kind - (optional) is a type of string
  kind = null
  # location - (required) is a type of string
  location = null
  # maximum_elastic_worker_count - (optional) is a type of number
  maximum_elastic_worker_count = null
  # name - (required) is a type of string
  name = null
  # per_site_scaling - (optional) is a type of bool
  per_site_scaling = null
  # reserved - (optional) is a type of bool
  reserved = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  sku = [{
    capacity = null
    size     = null
    tier     = null
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
variable "app_service_environment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_xenon" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kind" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "maximum_elastic_worker_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "per_site_scaling" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "reserved" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      size     = string
      tier     = string
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
resource "azurerm_app_service_plan" "this" {
  # app_service_environment_id - (optional) is a type of string
  app_service_environment_id = var.app_service_environment_id
  # is_xenon - (optional) is a type of bool
  is_xenon = var.is_xenon
  # kind - (optional) is a type of string
  kind = var.kind
  # location - (required) is a type of string
  location = var.location
  # maximum_elastic_worker_count - (optional) is a type of number
  maximum_elastic_worker_count = var.maximum_elastic_worker_count
  # name - (required) is a type of string
  name = var.name
  # per_site_scaling - (optional) is a type of bool
  per_site_scaling = var.per_site_scaling
  # reserved - (optional) is a type of bool
  reserved = var.reserved
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "sku" {
    for_each = var.sku
    content {
      # capacity - (optional) is a type of number
      capacity = sku.value["capacity"]
      # size - (required) is a type of string
      size = sku.value["size"]
      # tier - (required) is a type of string
      tier = sku.value["tier"]
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
  value       = azurerm_app_service_plan.this.id
}

output "maximum_elastic_worker_count" {
  description = "returns a number"
  value       = azurerm_app_service_plan.this.maximum_elastic_worker_count
}

output "maximum_number_of_workers" {
  description = "returns a number"
  value       = azurerm_app_service_plan.this.maximum_number_of_workers
}

output "this" {
  value = azurerm_app_service_plan.this
}
```

[top](#index)