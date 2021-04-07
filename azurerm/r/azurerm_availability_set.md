# azurerm_availability_set

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
module "azurerm_availability_set" {
  source = "./modules/azurerm/r/azurerm_availability_set"

  # location - (required) is a type of string
  location = null
  # managed - (optional) is a type of bool
  managed = null
  # name - (required) is a type of string
  name = null
  # platform_fault_domain_count - (optional) is a type of number
  platform_fault_domain_count = null
  # platform_update_domain_count - (optional) is a type of number
  platform_update_domain_count = null
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "managed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "platform_fault_domain_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "platform_update_domain_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proximity_placement_group_id" {
  description = "(optional)"
  type        = string
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
resource "azurerm_availability_set" "this" {
  # location - (required) is a type of string
  location = var.location
  # managed - (optional) is a type of bool
  managed = var.managed
  # name - (required) is a type of string
  name = var.name
  # platform_fault_domain_count - (optional) is a type of number
  platform_fault_domain_count = var.platform_fault_domain_count
  # platform_update_domain_count - (optional) is a type of number
  platform_update_domain_count = var.platform_update_domain_count
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = var.proximity_placement_group_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

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
  value       = azurerm_availability_set.this.id
}

output "this" {
  value = azurerm_availability_set.this
}
```

[top](#index)