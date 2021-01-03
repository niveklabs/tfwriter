# alicloud_log_alert

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_log_alert" {
  source = "./modules/alicloud/r/alicloud_log_alert"

  # alert_description - (optional) is a type of string
  alert_description = null
  # alert_displayname - (required) is a type of string
  alert_displayname = null
  # alert_name - (required) is a type of string
  alert_name = null
  # condition - (required) is a type of string
  condition = null
  # dashboard - (required) is a type of string
  dashboard = null
  # mute_until - (optional) is a type of number
  mute_until = null
  # notify_threshold - (optional) is a type of number
  notify_threshold = null
  # project_name - (required) is a type of string
  project_name = null
  # schedule_interval - (optional) is a type of string
  schedule_interval = null
  # schedule_type - (optional) is a type of string
  schedule_type = null
  # throttling - (optional) is a type of string
  throttling = null

  notification_list = [{
    content     = null
    email_list  = []
    mobile_list = []
    service_uri = null
    type        = null
  }]

  query_list = [{
    chart_title    = null
    end            = null
    logstore       = null
    query          = null
    start          = null
    time_span_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alert_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_displayname" {
  description = "(required)"
  type        = string
}

variable "alert_name" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "(required)"
  type        = string
}

variable "dashboard" {
  description = "(required)"
  type        = string
}

variable "mute_until" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notify_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "project_name" {
  description = "(required)"
  type        = string
}

variable "schedule_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "throttling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_list" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      content     = string
      email_list  = set(string)
      mobile_list = set(string)
      service_uri = string
      type        = string
    }
  ))
}

variable "query_list" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      chart_title    = string
      end            = string
      logstore       = string
      query          = string
      start          = string
      time_span_type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_log_alert" "this" {
  alert_description = var.alert_description
  alert_displayname = var.alert_displayname
  alert_name        = var.alert_name
  condition         = var.condition
  dashboard         = var.dashboard
  mute_until        = var.mute_until
  notify_threshold  = var.notify_threshold
  project_name      = var.project_name
  schedule_interval = var.schedule_interval
  schedule_type     = var.schedule_type
  throttling        = var.throttling

  dynamic "notification_list" {
    for_each = var.notification_list
    content {
      content     = notification_list.value["content"]
      email_list  = notification_list.value["email_list"]
      mobile_list = notification_list.value["mobile_list"]
      service_uri = notification_list.value["service_uri"]
      type        = notification_list.value["type"]
    }
  }

  dynamic "query_list" {
    for_each = var.query_list
    content {
      chart_title    = query_list.value["chart_title"]
      end            = query_list.value["end"]
      logstore       = query_list.value["logstore"]
      query          = query_list.value["query"]
      start          = query_list.value["start"]
      time_span_type = query_list.value["time_span_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_log_alert.this.id
}

output "this" {
  value = alicloud_log_alert.this
}
```

[top](#index)