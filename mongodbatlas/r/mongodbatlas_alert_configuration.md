# mongodbatlas_alert_configuration

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_alert_configuration" {
  source = "./modules/mongodbatlas/r/mongodbatlas_alert_configuration"

  # enabled - (optional) is a type of bool
  enabled = null
  # event_type - (required) is a type of string
  event_type = null
  # metric_threshold - (optional) is a type of map of string
  metric_threshold = {}
  # project_id - (required) is a type of string
  project_id = null
  # threshold - (optional) is a type of map of string
  threshold = {}

  matcher = [{
    field_name = null
    operator   = null
    value      = null
  }]

  notification = [{
    api_token              = null
    channel_name           = null
    datadog_api_key        = null
    datadog_region         = null
    delay_min              = null
    email_address          = null
    email_enabled          = null
    flow_name              = null
    flowdock_api_token     = null
    interval_min           = null
    mobile_number          = null
    ops_genie_api_key      = null
    ops_genie_region       = null
    org_name               = null
    roles                  = []
    service_key            = null
    sms_enabled            = null
    team_id                = null
    type_name              = null
    username               = null
    victor_ops_api_key     = null
    victor_ops_routing_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "event_type" {
  description = "(required)"
  type        = string
}

variable "metric_threshold" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "threshold" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "matcher" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      field_name = string
      operator   = string
      value      = string
    }
  ))
  default = []
}

variable "notification" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      api_token              = string
      channel_name           = string
      datadog_api_key        = string
      datadog_region         = string
      delay_min              = number
      email_address          = string
      email_enabled          = bool
      flow_name              = string
      flowdock_api_token     = string
      interval_min           = number
      mobile_number          = string
      ops_genie_api_key      = string
      ops_genie_region       = string
      org_name               = string
      roles                  = list(string)
      service_key            = string
      sms_enabled            = bool
      team_id                = string
      type_name              = string
      username               = string
      victor_ops_api_key     = string
      victor_ops_routing_key = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_alert_configuration" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # event_type - (required) is a type of string
  event_type = var.event_type
  # metric_threshold - (optional) is a type of map of string
  metric_threshold = var.metric_threshold
  # project_id - (required) is a type of string
  project_id = var.project_id
  # threshold - (optional) is a type of map of string
  threshold = var.threshold

  dynamic "matcher" {
    for_each = var.matcher
    content {
      # field_name - (optional) is a type of string
      field_name = matcher.value["field_name"]
      # operator - (optional) is a type of string
      operator = matcher.value["operator"]
      # value - (optional) is a type of string
      value = matcher.value["value"]
    }
  }

  dynamic "notification" {
    for_each = var.notification
    content {
      # api_token - (optional) is a type of string
      api_token = notification.value["api_token"]
      # channel_name - (optional) is a type of string
      channel_name = notification.value["channel_name"]
      # datadog_api_key - (optional) is a type of string
      datadog_api_key = notification.value["datadog_api_key"]
      # datadog_region - (optional) is a type of string
      datadog_region = notification.value["datadog_region"]
      # delay_min - (optional) is a type of number
      delay_min = notification.value["delay_min"]
      # email_address - (optional) is a type of string
      email_address = notification.value["email_address"]
      # email_enabled - (optional) is a type of bool
      email_enabled = notification.value["email_enabled"]
      # flow_name - (optional) is a type of string
      flow_name = notification.value["flow_name"]
      # flowdock_api_token - (optional) is a type of string
      flowdock_api_token = notification.value["flowdock_api_token"]
      # interval_min - (optional) is a type of number
      interval_min = notification.value["interval_min"]
      # mobile_number - (optional) is a type of string
      mobile_number = notification.value["mobile_number"]
      # ops_genie_api_key - (optional) is a type of string
      ops_genie_api_key = notification.value["ops_genie_api_key"]
      # ops_genie_region - (optional) is a type of string
      ops_genie_region = notification.value["ops_genie_region"]
      # org_name - (optional) is a type of string
      org_name = notification.value["org_name"]
      # roles - (optional) is a type of list of string
      roles = notification.value["roles"]
      # service_key - (optional) is a type of string
      service_key = notification.value["service_key"]
      # sms_enabled - (optional) is a type of bool
      sms_enabled = notification.value["sms_enabled"]
      # team_id - (optional) is a type of string
      team_id = notification.value["team_id"]
      # type_name - (optional) is a type of string
      type_name = notification.value["type_name"]
      # username - (optional) is a type of string
      username = notification.value["username"]
      # victor_ops_api_key - (optional) is a type of string
      victor_ops_api_key = notification.value["victor_ops_api_key"]
      # victor_ops_routing_key - (optional) is a type of string
      victor_ops_routing_key = notification.value["victor_ops_routing_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alert_configuration_id" {
  description = "returns a string"
  value       = mongodbatlas_alert_configuration.this.alert_configuration_id
}

output "created" {
  description = "returns a string"
  value       = mongodbatlas_alert_configuration.this.created
}

output "enabled" {
  description = "returns a bool"
  value       = mongodbatlas_alert_configuration.this.enabled
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_alert_configuration.this.id
}

output "updated" {
  description = "returns a string"
  value       = mongodbatlas_alert_configuration.this.updated
}

output "this" {
  value = mongodbatlas_alert_configuration.this
}
```

[top](#index)