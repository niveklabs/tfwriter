# azurerm_hpc_cache_nfs_target

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
module "azurerm_hpc_cache_nfs_target" {
  source = "./modules/azurerm/r/azurerm_hpc_cache_nfs_target"

  # cache_name - (required) is a type of string
  cache_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # target_host_name - (required) is a type of string
  target_host_name = null
  # usage_model - (required) is a type of string
  usage_model = null

  namespace_junction = [{
    namespace_path = null
    nfs_export     = null
    target_path    = null
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
variable "cache_name" {
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

variable "target_host_name" {
  description = "(required)"
  type        = string
}

variable "usage_model" {
  description = "(required)"
  type        = string
}

variable "namespace_junction" {
  description = "nested block: NestingSet, min items: 1, max items: 10"
  type = set(object(
    {
      namespace_path = string
      nfs_export     = string
      target_path    = string
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
resource "azurerm_hpc_cache_nfs_target" "this" {
  cache_name          = var.cache_name
  name                = var.name
  resource_group_name = var.resource_group_name
  target_host_name    = var.target_host_name
  usage_model         = var.usage_model

  dynamic "namespace_junction" {
    for_each = var.namespace_junction
    content {
      namespace_path = namespace_junction.value["namespace_path"]
      nfs_export     = namespace_junction.value["nfs_export"]
      target_path    = namespace_junction.value["target_path"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_hpc_cache_nfs_target.this.id
}

output "this" {
  value = azurerm_hpc_cache_nfs_target.this
}
```

[top](#index)