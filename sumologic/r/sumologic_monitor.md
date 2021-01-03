# sumologic_monitor

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.6.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_monitor" {
  source = "./modules/sumologic/r/sumologic_monitor"

  # content_type - (optional) is a type of string
  content_type = null
  # created_at - (optional) is a type of string
  created_at = null
  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # group_notifications - (optional) is a type of bool
  group_notifications = null
  # is_disabled - (optional) is a type of bool
  is_disabled = null
  # is_locked - (optional) is a type of bool
  is_locked = null
  # is_mutable - (optional) is a type of bool
  is_mutable = null
  # is_system - (optional) is a type of bool
  is_system = null
  # modified_at - (optional) is a type of string
  modified_at = null
  # modified_by - (optional) is a type of string
  modified_by = null
  # monitor_type - (required) is a type of string
  monitor_type = null
  # name - (required) is a type of string
  name = null
  # parent_id - (optional) is a type of string
  parent_id = null
  # post_request_map - (optional) is a type of map of string
  post_request_map = {}
  # status - (optional) is a type of list of string
  status = []
  # type - (optional) is a type of string
  type = null
  # version - (optional) is a type of number
  version = null

  notifications = [{
    notification = [{
      action_type      = null
      connection_id    = null
      connection_type  = null
      message_body     = null
      payload_override = null
      recipients       = []
      subject          = null
      time_zone        = null
    }]
    run_for_trigger_types = []
  }]

  queries = [{
    query  = null
    row_id = null
  }]

  triggers = [{
    detection_method = null
    occurrence_type  = null
    threshold        = null
    threshold_type   = null
    time_range       = null
    trigger_source   = null
    trigger_type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_notifications" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_locked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_mutable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_system" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "modified_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "modified_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "post_request_map" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notifications" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      notification = list(object(
        {
          action_type      = string
          connection_id    = string
          connection_type  = string
          message_body     = string
          payload_override = string
          recipients       = list(string)
          subject          = string
          time_zone        = string
        }
      ))
      run_for_trigger_types = list(string)
    }
  ))
  default = []
}

variable "queries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      query  = string
      row_id = string
    }
  ))
  default = []
}

variable "triggers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      detection_method = string
      occurrence_type  = string
      threshold        = number
      threshold_type   = string
      time_range       = string
      trigger_source   = string
      trigger_type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_monitor" "this" {
  content_type        = var.content_type
  created_at          = var.created_at
  created_by          = var.created_by
  description         = var.description
  group_notifications = var.group_notifications
  is_disabled         = var.is_disabled
  is_locked           = var.is_locked
  is_mutable          = var.is_mutable
  is_system           = var.is_system
  modified_at         = var.modified_at
  modified_by         = var.modified_by
  monitor_type        = var.monitor_type
  name                = var.name
  parent_id           = var.parent_id
  post_request_map    = var.post_request_map
  status              = var.status
  type                = var.type
  version             = var.version

  dynamic "notifications" {
    for_each = var.notifications
    content {
      run_for_trigger_types = notifications.value["run_for_trigger_types"]

      dynamic "notification" {
        for_each = notifications.value.notification
        content {
          action_type      = notification.value["action_type"]
          connection_id    = notification.value["connection_id"]
          connection_type  = notification.value["connection_type"]
          message_body     = notification.value["message_body"]
          payload_override = notification.value["payload_override"]
          recipients       = notification.value["recipients"]
          subject          = notification.value["subject"]
          time_zone        = notification.value["time_zone"]
        }
      }

    }
  }

  dynamic "queries" {
    for_each = var.queries
    content {
      query  = queries.value["query"]
      row_id = queries.value["row_id"]
    }
  }

  dynamic "triggers" {
    for_each = var.triggers
    content {
      detection_method = triggers.value["detection_method"]
      occurrence_type  = triggers.value["occurrence_type"]
      threshold        = triggers.value["threshold"]
      threshold_type   = triggers.value["threshold_type"]
      time_range       = triggers.value["time_range"]
      trigger_source   = triggers.value["trigger_source"]
      trigger_type     = triggers.value["trigger_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = sumologic_monitor.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = sumologic_monitor.this.created_by
}

output "id" {
  description = "returns a string"
  value       = sumologic_monitor.this.id
}

output "is_locked" {
  description = "returns a bool"
  value       = sumologic_monitor.this.is_locked
}

output "is_mutable" {
  description = "returns a bool"
  value       = sumologic_monitor.this.is_mutable
}

output "is_system" {
  description = "returns a bool"
  value       = sumologic_monitor.this.is_system
}

output "modified_at" {
  description = "returns a string"
  value       = sumologic_monitor.this.modified_at
}

output "modified_by" {
  description = "returns a string"
  value       = sumologic_monitor.this.modified_by
}

output "parent_id" {
  description = "returns a string"
  value       = sumologic_monitor.this.parent_id
}

output "status" {
  description = "returns a list of string"
  value       = sumologic_monitor.this.status
}

output "version" {
  description = "returns a number"
  value       = sumologic_monitor.this.version
}

output "this" {
  value = sumologic_monitor.this
}
```

[top](#index)