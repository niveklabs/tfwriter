# azurerm_stream_analytics_reference_input_blob

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
module "azurerm_stream_analytics_reference_input_blob" {
  source = "./modules/azurerm/r/azurerm_stream_analytics_reference_input_blob"

  # date_format - (required) is a type of string
  date_format = null
  # name - (required) is a type of string
  name = null
  # path_pattern - (required) is a type of string
  path_pattern = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_key - (required) is a type of string
  storage_account_key = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null
  # storage_container_name - (required) is a type of string
  storage_container_name = null
  # stream_analytics_job_name - (required) is a type of string
  stream_analytics_job_name = null
  # time_format - (required) is a type of string
  time_format = null

  serialization = [{
    encoding        = null
    field_delimiter = null
    type            = null
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
variable "date_format" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "path_pattern" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_account_key" {
  description = "(required)"
  type        = string
}

variable "storage_account_name" {
  description = "(required)"
  type        = string
}

variable "storage_container_name" {
  description = "(required)"
  type        = string
}

variable "stream_analytics_job_name" {
  description = "(required)"
  type        = string
}

variable "time_format" {
  description = "(required)"
  type        = string
}

variable "serialization" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      encoding        = string
      field_delimiter = string
      type            = string
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
resource "azurerm_stream_analytics_reference_input_blob" "this" {
  date_format               = var.date_format
  name                      = var.name
  path_pattern              = var.path_pattern
  resource_group_name       = var.resource_group_name
  storage_account_key       = var.storage_account_key
  storage_account_name      = var.storage_account_name
  storage_container_name    = var.storage_container_name
  stream_analytics_job_name = var.stream_analytics_job_name
  time_format               = var.time_format

  dynamic "serialization" {
    for_each = var.serialization
    content {
      encoding        = serialization.value["encoding"]
      field_delimiter = serialization.value["field_delimiter"]
      type            = serialization.value["type"]
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
  value       = azurerm_stream_analytics_reference_input_blob.this.id
}

output "this" {
  value = azurerm_stream_analytics_reference_input_blob.this
}
```

[top](#index)