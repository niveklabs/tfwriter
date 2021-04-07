# azurerm_hpc_cache_blob_target

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
module "azurerm_hpc_cache_blob_target" {
  source = "./modules/azurerm/r/azurerm_hpc_cache_blob_target"

  # access_policy_name - (optional) is a type of string
  access_policy_name = null
  # cache_name - (required) is a type of string
  cache_name = null
  # name - (required) is a type of string
  name = null
  # namespace_path - (required) is a type of string
  namespace_path = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_container_id - (required) is a type of string
  storage_container_id = null

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
variable "access_policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_path" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_container_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_hpc_cache_blob_target" "this" {
  # access_policy_name - (optional) is a type of string
  access_policy_name = var.access_policy_name
  # cache_name - (required) is a type of string
  cache_name = var.cache_name
  # name - (required) is a type of string
  name = var.name
  # namespace_path - (required) is a type of string
  namespace_path = var.namespace_path
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # storage_container_id - (required) is a type of string
  storage_container_id = var.storage_container_id

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
output "access_policy_name" {
  description = "returns a string"
  value       = azurerm_hpc_cache_blob_target.this.access_policy_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_hpc_cache_blob_target.this.id
}

output "this" {
  value = azurerm_hpc_cache_blob_target.this
}
```

[top](#index)