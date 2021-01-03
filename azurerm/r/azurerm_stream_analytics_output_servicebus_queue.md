# azurerm_stream_analytics_output_servicebus_queue

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
module "azurerm_stream_analytics_output_servicebus_queue" {
  source = "./modules/azurerm/r/azurerm_stream_analytics_output_servicebus_queue"

  # name - (required) is a type of string
  name = null
  # queue_name - (required) is a type of string
  queue_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # servicebus_namespace - (required) is a type of string
  servicebus_namespace = null
  # shared_access_policy_key - (required) is a type of string
  shared_access_policy_key = null
  # shared_access_policy_name - (required) is a type of string
  shared_access_policy_name = null
  # stream_analytics_job_name - (required) is a type of string
  stream_analytics_job_name = null

  serialization = [{
    encoding        = null
    field_delimiter = null
    format          = null
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
variable "name" {
  description = "(required)"
  type        = string
}

variable "queue_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "servicebus_namespace" {
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
      format          = string
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
resource "azurerm_stream_analytics_output_servicebus_queue" "this" {
  name                      = var.name
  queue_name                = var.queue_name
  resource_group_name       = var.resource_group_name
  servicebus_namespace      = var.servicebus_namespace
  shared_access_policy_key  = var.shared_access_policy_key
  shared_access_policy_name = var.shared_access_policy_name
  stream_analytics_job_name = var.stream_analytics_job_name

  dynamic "serialization" {
    for_each = var.serialization
    content {
      encoding        = serialization.value["encoding"]
      field_delimiter = serialization.value["field_delimiter"]
      format          = serialization.value["format"]
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
  value       = azurerm_stream_analytics_output_servicebus_queue.this.id
}

output "this" {
  value = azurerm_stream_analytics_output_servicebus_queue.this
}
```

[top](#index)