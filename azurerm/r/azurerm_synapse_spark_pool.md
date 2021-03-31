# azurerm_synapse_spark_pool

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
module "azurerm_synapse_spark_pool" {
  source = "./modules/azurerm/r/azurerm_synapse_spark_pool"

  # name - (required) is a type of string
  name = null
  # node_count - (optional) is a type of number
  node_count = null
  # node_size - (required) is a type of string
  node_size = null
  # node_size_family - (required) is a type of string
  node_size_family = null
  # spark_events_folder - (optional) is a type of string
  spark_events_folder = null
  # spark_log_folder - (optional) is a type of string
  spark_log_folder = null
  # spark_version - (optional) is a type of string
  spark_version = null
  # synapse_workspace_id - (required) is a type of string
  synapse_workspace_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  auto_pause = [{
    delay_in_minutes = null
  }]

  auto_scale = [{
    max_node_count = null
    min_node_count = null
  }]

  library_requirement = [{
    content  = null
    filename = null
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
variable "name" {
  description = "(required)"
  type        = string
}

variable "node_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "node_size" {
  description = "(required)"
  type        = string
}

variable "node_size_family" {
  description = "(required)"
  type        = string
}

variable "spark_events_folder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spark_log_folder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spark_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "synapse_workspace_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "auto_pause" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delay_in_minutes = number
    }
  ))
  default = []
}

variable "auto_scale" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_node_count = number
      min_node_count = number
    }
  ))
  default = []
}

variable "library_requirement" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content  = string
      filename = string
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
resource "azurerm_synapse_spark_pool" "this" {
  name                 = var.name
  node_count           = var.node_count
  node_size            = var.node_size
  node_size_family     = var.node_size_family
  spark_events_folder  = var.spark_events_folder
  spark_log_folder     = var.spark_log_folder
  spark_version        = var.spark_version
  synapse_workspace_id = var.synapse_workspace_id
  tags                 = var.tags

  dynamic "auto_pause" {
    for_each = var.auto_pause
    content {
      delay_in_minutes = auto_pause.value["delay_in_minutes"]
    }
  }

  dynamic "auto_scale" {
    for_each = var.auto_scale
    content {
      max_node_count = auto_scale.value["max_node_count"]
      min_node_count = auto_scale.value["min_node_count"]
    }
  }

  dynamic "library_requirement" {
    for_each = var.library_requirement
    content {
      content  = library_requirement.value["content"]
      filename = library_requirement.value["filename"]
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
  value       = azurerm_synapse_spark_pool.this.id
}

output "this" {
  value = azurerm_synapse_spark_pool.this
}
```

[top](#index)