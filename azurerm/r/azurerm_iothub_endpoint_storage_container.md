# azurerm_iothub_endpoint_storage_container

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
module "azurerm_iothub_endpoint_storage_container" {
  source = "./modules/azurerm/r/azurerm_iothub_endpoint_storage_container"

  # batch_frequency_in_seconds - (optional) is a type of number
  batch_frequency_in_seconds = null
  # connection_string - (required) is a type of string
  connection_string = null
  # container_name - (required) is a type of string
  container_name = null
  # encoding - (optional) is a type of string
  encoding = null
  # file_name_format - (optional) is a type of string
  file_name_format = null
  # iothub_name - (required) is a type of string
  iothub_name = null
  # max_chunk_size_in_bytes - (optional) is a type of number
  max_chunk_size_in_bytes = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "batch_frequency_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "connection_string" {
  description = "(required)"
  type        = string
}

variable "container_name" {
  description = "(required)"
  type        = string
}

variable "encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_name_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iothub_name" {
  description = "(required)"
  type        = string
}

variable "max_chunk_size_in_bytes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
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
resource "azurerm_iothub_endpoint_storage_container" "this" {
  batch_frequency_in_seconds = var.batch_frequency_in_seconds
  connection_string          = var.connection_string
  container_name             = var.container_name
  encoding                   = var.encoding
  file_name_format           = var.file_name_format
  iothub_name                = var.iothub_name
  max_chunk_size_in_bytes    = var.max_chunk_size_in_bytes
  name                       = var.name
  resource_group_name        = var.resource_group_name

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
  value       = azurerm_iothub_endpoint_storage_container.this.id
}

output "this" {
  value = azurerm_iothub_endpoint_storage_container.this
}
```

[top](#index)