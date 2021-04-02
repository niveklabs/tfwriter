# azurerm_stream_analytics_stream_input_iothub

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
module "azurerm_stream_analytics_stream_input_iothub" {
  source = "./modules/azurerm/r/azurerm_stream_analytics_stream_input_iothub"

  # endpoint - (required) is a type of string
  endpoint = null
  # eventhub_consumer_group_name - (required) is a type of string
  eventhub_consumer_group_name = null
  # iothub_namespace - (required) is a type of string
  iothub_namespace = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # shared_access_policy_key - (required) is a type of string
  shared_access_policy_key = null
  # shared_access_policy_name - (required) is a type of string
  shared_access_policy_name = null
  # stream_analytics_job_name - (required) is a type of string
  stream_analytics_job_name = null

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
variable "endpoint" {
  description = "(required)"
  type        = string
}

variable "eventhub_consumer_group_name" {
  description = "(required)"
  type        = string
}

variable "iothub_namespace" {
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

variable "shared_access_policy_key" {
  description = "(required)"
  type        = string
}

variable "shared_access_policy_name" {
  description = "(required)"
  type        = string
}

variable "stream_analytics_job_name" {
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
resource "azurerm_stream_analytics_stream_input_iothub" "this" {
  endpoint                     = var.endpoint
  eventhub_consumer_group_name = var.eventhub_consumer_group_name
  iothub_namespace             = var.iothub_namespace
  name                         = var.name
  resource_group_name          = var.resource_group_name
  shared_access_policy_key     = var.shared_access_policy_key
  shared_access_policy_name    = var.shared_access_policy_name
  stream_analytics_job_name    = var.stream_analytics_job_name

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
  value       = azurerm_stream_analytics_stream_input_iothub.this.id
}

output "this" {
  value = azurerm_stream_analytics_stream_input_iothub.this
}
```

[top](#index)