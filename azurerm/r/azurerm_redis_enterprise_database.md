# azurerm_redis_enterprise_database

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
module "azurerm_redis_enterprise_database" {
  source = "./modules/azurerm/r/azurerm_redis_enterprise_database"

  # client_protocol - (optional) is a type of string
  client_protocol = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # clustering_policy - (optional) is a type of string
  clustering_policy = null
  # eviction_policy - (optional) is a type of string
  eviction_policy = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  module = [{
    args    = null
    name    = null
    version = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "client_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "clustering_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eviction_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "module" {
  description = "nested block: NestingList, min items: 0, max items: 3"
  type = set(object(
    {
      args    = string
      name    = string
      version = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_redis_enterprise_database" "this" {
  client_protocol     = var.client_protocol
  cluster_id          = var.cluster_id
  clustering_policy   = var.clustering_policy
  eviction_policy     = var.eviction_policy
  name                = var.name
  port                = var.port
  resource_group_name = var.resource_group_name

  dynamic "module" {
    for_each = var.module
    content {
      args = module.value["args"]
      name = module.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_redis_enterprise_database.this.id
}

output "this" {
  value = azurerm_redis_enterprise_database.this
}
```

[top](#index)