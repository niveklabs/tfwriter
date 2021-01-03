# azurerm_eventhub

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_eventhub" {
  source = "./modules/azurerm/r/azurerm_eventhub"

  # message_retention - (required) is a type of number
  message_retention = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # partition_count - (required) is a type of number
  partition_count = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  capture_description = [{
    destination = [{
      archive_name_format = null
      blob_container_name = null
      name                = null
      storage_account_id  = null
    }]
    enabled             = null
    encoding            = null
    interval_in_seconds = null
    size_limit_in_bytes = null
    skip_empty_archives = null
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
variable "message_retention" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "partition_count" {
  description = "(required)"
  type        = number
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "capture_description" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      destination = list(object(
        {
          archive_name_format = string
          blob_container_name = string
          name                = string
          storage_account_id  = string
        }
      ))
      enabled             = bool
      encoding            = string
      interval_in_seconds = number
      size_limit_in_bytes = number
      skip_empty_archives = bool
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
resource "azurerm_eventhub" "this" {
  message_retention   = var.message_retention
  name                = var.name
  namespace_name      = var.namespace_name
  partition_count     = var.partition_count
  resource_group_name = var.resource_group_name

  dynamic "capture_description" {
    for_each = var.capture_description
    content {
      enabled             = capture_description.value["enabled"]
      encoding            = capture_description.value["encoding"]
      interval_in_seconds = capture_description.value["interval_in_seconds"]
      size_limit_in_bytes = capture_description.value["size_limit_in_bytes"]
      skip_empty_archives = capture_description.value["skip_empty_archives"]

      dynamic "destination" {
        for_each = capture_description.value.destination
        content {
          archive_name_format = destination.value["archive_name_format"]
          blob_container_name = destination.value["blob_container_name"]
          name                = destination.value["name"]
          storage_account_id  = destination.value["storage_account_id"]
        }
      }

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
  value       = azurerm_eventhub.this.id
}

output "partition_ids" {
  description = "returns a set of string"
  value       = azurerm_eventhub.this.partition_ids
}

output "this" {
  value = azurerm_eventhub.this
}
```

[top](#index)