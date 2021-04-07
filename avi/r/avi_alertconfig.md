# avi_alertconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_alertconfig" {
  source = null

  # action_group_ref - (optional) is a type of string
  action_group_ref = null
  # autoscale_alert - (optional) is a type of bool
  autoscale_alert = null
  # category - (required) is a type of string
  category = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # expiry_time - (optional) is a type of number
  expiry_time = null
  # name - (required) is a type of string
  name = null
  # obj_uuid - (optional) is a type of string
  obj_uuid = null
  # object_type - (optional) is a type of string
  object_type = null
  # recommendation - (optional) is a type of string
  recommendation = null
  # rolling_window - (optional) is a type of number
  rolling_window = null
  # source - (required) is a type of string
  # summary - (optional) is a type of string
  summary = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # threshold - (optional) is a type of number
  threshold = null
  # throttle - (optional) is a type of number
  throttle = null
  # uuid - (optional) is a type of string
  uuid = null

  alert_rule = [{
    conn_app_log_rule = [{
      filter_action = null
      filter_string = null
    }]
    event_match_filter = null
    metrics_rule = [{
      duration  = null
      metric_id = null
      metric_threshold = [{
        comparator = null
        threshold  = null
      }]
    }]
    operator = null
    sys_event_rule = [{
      event_details = [{
        comparator          = null
        event_details_key   = null
        event_details_value = null
      }]
      event_id = null
      not_cond = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action_group_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autoscale_alert" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "category" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "expiry_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "obj_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "object_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recommendation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rolling_window" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source" {
  description = "(required)"
  type        = string
}

variable "summary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "throttle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      conn_app_log_rule = set(object(
        {
          filter_action = string
          filter_string = string
        }
      ))
      event_match_filter = string
      metrics_rule = list(object(
        {
          duration  = number
          metric_id = string
          metric_threshold = set(object(
            {
              comparator = string
              threshold  = number
            }
          ))
        }
      ))
      operator = string
      sys_event_rule = list(object(
        {
          event_details = list(object(
            {
              comparator          = string
              event_details_key   = string
              event_details_value = string
            }
          ))
          event_id = string
          not_cond = bool
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "avi_alertconfig" "this" {
  # action_group_ref - (optional) is a type of string
  action_group_ref = var.action_group_ref
  # autoscale_alert - (optional) is a type of bool
  autoscale_alert = var.autoscale_alert
  # category - (required) is a type of string
  category = var.category
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # expiry_time - (optional) is a type of number
  expiry_time = var.expiry_time
  # name - (required) is a type of string
  name = var.name
  # obj_uuid - (optional) is a type of string
  obj_uuid = var.obj_uuid
  # object_type - (optional) is a type of string
  object_type = var.object_type
  # recommendation - (optional) is a type of string
  recommendation = var.recommendation
  # rolling_window - (optional) is a type of number
  rolling_window = var.rolling_window
  # source - (required) is a type of string
  source = var.source
  # summary - (optional) is a type of string
  summary = var.summary
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # threshold - (optional) is a type of number
  threshold = var.threshold
  # throttle - (optional) is a type of number
  throttle = var.throttle
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "alert_rule" {
    for_each = var.alert_rule
    content {
      # event_match_filter - (optional) is a type of string
      event_match_filter = alert_rule.value["event_match_filter"]
      # operator - (optional) is a type of string
      operator = alert_rule.value["operator"]

      dynamic "conn_app_log_rule" {
        for_each = alert_rule.value.conn_app_log_rule
        content {
          # filter_action - (optional) is a type of string
          filter_action = conn_app_log_rule.value["filter_action"]
          # filter_string - (required) is a type of string
          filter_string = conn_app_log_rule.value["filter_string"]
        }
      }

      dynamic "metrics_rule" {
        for_each = alert_rule.value.metrics_rule
        content {
          # duration - (optional) is a type of number
          duration = metrics_rule.value["duration"]
          # metric_id - (optional) is a type of string
          metric_id = metrics_rule.value["metric_id"]

          dynamic "metric_threshold" {
            for_each = metrics_rule.value.metric_threshold
            content {
              # comparator - (required) is a type of string
              comparator = metric_threshold.value["comparator"]
              # threshold - (optional) is a type of number
              threshold = metric_threshold.value["threshold"]
            }
          }

        }
      }

      dynamic "sys_event_rule" {
        for_each = alert_rule.value.sys_event_rule
        content {
          # event_id - (optional) is a type of string
          event_id = sys_event_rule.value["event_id"]
          # not_cond - (optional) is a type of bool
          not_cond = sys_event_rule.value["not_cond"]

          dynamic "event_details" {
            for_each = sys_event_rule.value.event_details
            content {
              # comparator - (required) is a type of string
              comparator = event_details.value["comparator"]
              # event_details_key - (required) is a type of string
              event_details_key = event_details.value["event_details_key"]
              # event_details_value - (required) is a type of string
              event_details_value = event_details.value["event_details_value"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action_group_ref" {
  description = "returns a string"
  value       = avi_alertconfig.this.action_group_ref
}

output "autoscale_alert" {
  description = "returns a bool"
  value       = avi_alertconfig.this.autoscale_alert
}

output "description" {
  description = "returns a string"
  value       = avi_alertconfig.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_alertconfig.this.id
}

output "obj_uuid" {
  description = "returns a string"
  value       = avi_alertconfig.this.obj_uuid
}

output "object_type" {
  description = "returns a string"
  value       = avi_alertconfig.this.object_type
}

output "recommendation" {
  description = "returns a string"
  value       = avi_alertconfig.this.recommendation
}

output "summary" {
  description = "returns a string"
  value       = avi_alertconfig.this.summary
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_alertconfig.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_alertconfig.this.uuid
}

output "this" {
  value = avi_alertconfig.this
}
```

[top](#index)