# azurerm_eventgrid_event_subscription

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
module "azurerm_eventgrid_event_subscription" {
  source = "./modules/azurerm/r/azurerm_eventgrid_event_subscription"

  # event_delivery_schema - (optional) is a type of string
  event_delivery_schema = null
  # eventhub_endpoint_id - (optional) is a type of string
  eventhub_endpoint_id = null
  # expiration_time_utc - (optional) is a type of string
  expiration_time_utc = null
  # hybrid_connection_endpoint_id - (optional) is a type of string
  hybrid_connection_endpoint_id = null
  # included_event_types - (optional) is a type of list of string
  included_event_types = []
  # labels - (optional) is a type of list of string
  labels = []
  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
  # service_bus_queue_endpoint_id - (optional) is a type of string
  service_bus_queue_endpoint_id = null
  # service_bus_topic_endpoint_id - (optional) is a type of string
  service_bus_topic_endpoint_id = null
  # topic_name - (optional) is a type of string
  topic_name = null

  advanced_filter = [{
    bool_equals = [{
      key   = null
      value = null
    }]
    number_greater_than = [{
      key   = null
      value = null
    }]
    number_greater_than_or_equals = [{
      key   = null
      value = null
    }]
    number_in = [{
      key    = null
      values = []
    }]
    number_less_than = [{
      key   = null
      value = null
    }]
    number_less_than_or_equals = [{
      key   = null
      value = null
    }]
    number_not_in = [{
      key    = null
      values = []
    }]
    string_begins_with = [{
      key    = null
      values = []
    }]
    string_contains = [{
      key    = null
      values = []
    }]
    string_ends_with = [{
      key    = null
      values = []
    }]
    string_in = [{
      key    = null
      values = []
    }]
    string_not_in = [{
      key    = null
      values = []
    }]
  }]

  azure_function_endpoint = [{
    function_id                       = null
    max_events_per_batch              = null
    preferred_batch_size_in_kilobytes = null
  }]

  eventhub_endpoint = [{
    eventhub_id = null
  }]

  hybrid_connection_endpoint = [{
    hybrid_connection_id = null
  }]

  retry_policy = [{
    event_time_to_live    = null
    max_delivery_attempts = null
  }]

  storage_blob_dead_letter_destination = [{
    storage_account_id          = null
    storage_blob_container_name = null
  }]

  storage_queue_endpoint = [{
    queue_name         = null
    storage_account_id = null
  }]

  subject_filter = [{
    case_sensitive      = null
    subject_begins_with = null
    subject_ends_with   = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  webhook_endpoint = [{
    active_directory_app_id_or_uri    = null
    active_directory_tenant_id        = null
    base_url                          = null
    max_events_per_batch              = null
    preferred_batch_size_in_kilobytes = null
    url                               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "event_delivery_schema" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eventhub_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiration_time_utc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hybrid_connection_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "included_event_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "service_bus_queue_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_bus_topic_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "topic_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "advanced_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bool_equals = list(object(
        {
          key   = string
          value = bool
        }
      ))
      number_greater_than = list(object(
        {
          key   = string
          value = number
        }
      ))
      number_greater_than_or_equals = list(object(
        {
          key   = string
          value = number
        }
      ))
      number_in = list(object(
        {
          key    = string
          values = list(number)
        }
      ))
      number_less_than = list(object(
        {
          key   = string
          value = number
        }
      ))
      number_less_than_or_equals = list(object(
        {
          key   = string
          value = number
        }
      ))
      number_not_in = list(object(
        {
          key    = string
          values = list(number)
        }
      ))
      string_begins_with = list(object(
        {
          key    = string
          values = list(string)
        }
      ))
      string_contains = list(object(
        {
          key    = string
          values = list(string)
        }
      ))
      string_ends_with = list(object(
        {
          key    = string
          values = list(string)
        }
      ))
      string_in = list(object(
        {
          key    = string
          values = list(string)
        }
      ))
      string_not_in = list(object(
        {
          key    = string
          values = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "azure_function_endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      function_id                       = string
      max_events_per_batch              = number
      preferred_batch_size_in_kilobytes = number
    }
  ))
  default = []
}

variable "eventhub_endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      eventhub_id = string
    }
  ))
  default = []
}

variable "hybrid_connection_endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      hybrid_connection_id = string
    }
  ))
  default = []
}

variable "retry_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      event_time_to_live    = number
      max_delivery_attempts = number
    }
  ))
  default = []
}

variable "storage_blob_dead_letter_destination" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      storage_account_id          = string
      storage_blob_container_name = string
    }
  ))
  default = []
}

variable "storage_queue_endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      queue_name         = string
      storage_account_id = string
    }
  ))
  default = []
}

variable "subject_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      case_sensitive      = bool
      subject_begins_with = string
      subject_ends_with   = string
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

variable "webhook_endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      active_directory_app_id_or_uri    = string
      active_directory_tenant_id        = string
      base_url                          = string
      max_events_per_batch              = number
      preferred_batch_size_in_kilobytes = number
      url                               = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_eventgrid_event_subscription" "this" {
  event_delivery_schema         = var.event_delivery_schema
  eventhub_endpoint_id          = var.eventhub_endpoint_id
  expiration_time_utc           = var.expiration_time_utc
  hybrid_connection_endpoint_id = var.hybrid_connection_endpoint_id
  included_event_types          = var.included_event_types
  labels                        = var.labels
  name                          = var.name
  scope                         = var.scope
  service_bus_queue_endpoint_id = var.service_bus_queue_endpoint_id
  service_bus_topic_endpoint_id = var.service_bus_topic_endpoint_id
  topic_name                    = var.topic_name

  dynamic "advanced_filter" {
    for_each = var.advanced_filter
    content {

      dynamic "bool_equals" {
        for_each = advanced_filter.value.bool_equals
        content {
          key   = bool_equals.value["key"]
          value = bool_equals.value["value"]
        }
      }

      dynamic "number_greater_than" {
        for_each = advanced_filter.value.number_greater_than
        content {
          key   = number_greater_than.value["key"]
          value = number_greater_than.value["value"]
        }
      }

      dynamic "number_greater_than_or_equals" {
        for_each = advanced_filter.value.number_greater_than_or_equals
        content {
          key   = number_greater_than_or_equals.value["key"]
          value = number_greater_than_or_equals.value["value"]
        }
      }

      dynamic "number_in" {
        for_each = advanced_filter.value.number_in
        content {
          key    = number_in.value["key"]
          values = number_in.value["values"]
        }
      }

      dynamic "number_less_than" {
        for_each = advanced_filter.value.number_less_than
        content {
          key   = number_less_than.value["key"]
          value = number_less_than.value["value"]
        }
      }

      dynamic "number_less_than_or_equals" {
        for_each = advanced_filter.value.number_less_than_or_equals
        content {
          key   = number_less_than_or_equals.value["key"]
          value = number_less_than_or_equals.value["value"]
        }
      }

      dynamic "number_not_in" {
        for_each = advanced_filter.value.number_not_in
        content {
          key    = number_not_in.value["key"]
          values = number_not_in.value["values"]
        }
      }

      dynamic "string_begins_with" {
        for_each = advanced_filter.value.string_begins_with
        content {
          key    = string_begins_with.value["key"]
          values = string_begins_with.value["values"]
        }
      }

      dynamic "string_contains" {
        for_each = advanced_filter.value.string_contains
        content {
          key    = string_contains.value["key"]
          values = string_contains.value["values"]
        }
      }

      dynamic "string_ends_with" {
        for_each = advanced_filter.value.string_ends_with
        content {
          key    = string_ends_with.value["key"]
          values = string_ends_with.value["values"]
        }
      }

      dynamic "string_in" {
        for_each = advanced_filter.value.string_in
        content {
          key    = string_in.value["key"]
          values = string_in.value["values"]
        }
      }

      dynamic "string_not_in" {
        for_each = advanced_filter.value.string_not_in
        content {
          key    = string_not_in.value["key"]
          values = string_not_in.value["values"]
        }
      }

    }
  }

  dynamic "azure_function_endpoint" {
    for_each = var.azure_function_endpoint
    content {
      function_id                       = azure_function_endpoint.value["function_id"]
      max_events_per_batch              = azure_function_endpoint.value["max_events_per_batch"]
      preferred_batch_size_in_kilobytes = azure_function_endpoint.value["preferred_batch_size_in_kilobytes"]
    }
  }

  dynamic "eventhub_endpoint" {
    for_each = var.eventhub_endpoint
    content {
      eventhub_id = eventhub_endpoint.value["eventhub_id"]
    }
  }

  dynamic "hybrid_connection_endpoint" {
    for_each = var.hybrid_connection_endpoint
    content {
      hybrid_connection_id = hybrid_connection_endpoint.value["hybrid_connection_id"]
    }
  }

  dynamic "retry_policy" {
    for_each = var.retry_policy
    content {
      event_time_to_live    = retry_policy.value["event_time_to_live"]
      max_delivery_attempts = retry_policy.value["max_delivery_attempts"]
    }
  }

  dynamic "storage_blob_dead_letter_destination" {
    for_each = var.storage_blob_dead_letter_destination
    content {
      storage_account_id          = storage_blob_dead_letter_destination.value["storage_account_id"]
      storage_blob_container_name = storage_blob_dead_letter_destination.value["storage_blob_container_name"]
    }
  }

  dynamic "storage_queue_endpoint" {
    for_each = var.storage_queue_endpoint
    content {
      queue_name         = storage_queue_endpoint.value["queue_name"]
      storage_account_id = storage_queue_endpoint.value["storage_account_id"]
    }
  }

  dynamic "subject_filter" {
    for_each = var.subject_filter
    content {
      case_sensitive      = subject_filter.value["case_sensitive"]
      subject_begins_with = subject_filter.value["subject_begins_with"]
      subject_ends_with   = subject_filter.value["subject_ends_with"]
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

  dynamic "webhook_endpoint" {
    for_each = var.webhook_endpoint
    content {
      active_directory_app_id_or_uri    = webhook_endpoint.value["active_directory_app_id_or_uri"]
      active_directory_tenant_id        = webhook_endpoint.value["active_directory_tenant_id"]
      max_events_per_batch              = webhook_endpoint.value["max_events_per_batch"]
      preferred_batch_size_in_kilobytes = webhook_endpoint.value["preferred_batch_size_in_kilobytes"]
      url                               = webhook_endpoint.value["url"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "eventhub_endpoint_id" {
  description = "returns a string"
  value       = azurerm_eventgrid_event_subscription.this.eventhub_endpoint_id
}

output "hybrid_connection_endpoint_id" {
  description = "returns a string"
  value       = azurerm_eventgrid_event_subscription.this.hybrid_connection_endpoint_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_eventgrid_event_subscription.this.id
}

output "included_event_types" {
  description = "returns a list of string"
  value       = azurerm_eventgrid_event_subscription.this.included_event_types
}

output "topic_name" {
  description = "returns a string"
  value       = azurerm_eventgrid_event_subscription.this.topic_name
}

output "this" {
  value = azurerm_eventgrid_event_subscription.this
}
```

[top](#index)