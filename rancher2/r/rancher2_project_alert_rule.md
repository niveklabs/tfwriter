# rancher2_project_alert_rule

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_project_alert_rule" {
  source = "./modules/rancher2/r/rancher2_project_alert_rule"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # group_id - (required) is a type of string
  group_id = null
  # group_interval_seconds - (optional) is a type of number
  group_interval_seconds = null
  # group_wait_seconds - (optional) is a type of number
  group_wait_seconds = null
  # inherited - (optional) is a type of bool
  inherited = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # repeat_interval_seconds - (optional) is a type of number
  repeat_interval_seconds = null
  # severity - (optional) is a type of string
  severity = null

  metric_rule = [{
    comparison      = null
    description     = null
    duration        = null
    expression      = null
    threshold_value = null
  }]

  pod_rule = [{
    condition                = null
    pod_id                   = null
    restart_interval_seconds = null
    restart_times            = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  workload_rule = [{
    available_percentage = null
    selector             = {}
    workload_id          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "group_id" {
  description = "(required) - Alert rule group ID"
  type        = string
}

variable "group_interval_seconds" {
  description = "(optional) - Alert rule interval seconds"
  type        = number
  default     = null
}

variable "group_wait_seconds" {
  description = "(optional) - Alert rule wait seconds"
  type        = number
  default     = null
}

variable "inherited" {
  description = "(optional) - Alert rule inherited"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Alert rule name"
  type        = string
}

variable "project_id" {
  description = "(required) - Alert rule Project ID"
  type        = string
}

variable "repeat_interval_seconds" {
  description = "(optional) - Alert rule repeat interval seconds"
  type        = number
  default     = null
}

variable "severity" {
  description = "(optional) - Alert rule severity"
  type        = string
  default     = null
}

variable "metric_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comparison      = string
      description     = string
      duration        = string
      expression      = string
      threshold_value = number
    }
  ))
  default = []
}

variable "pod_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      condition                = string
      pod_id                   = string
      restart_interval_seconds = number
      restart_times            = number
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
      update = string
    }
  ))
  default = []
}

variable "workload_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      available_percentage = number
      selector             = map(string)
      workload_id          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_project_alert_rule" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # group_id - (required) is a type of string
  group_id = var.group_id
  # group_interval_seconds - (optional) is a type of number
  group_interval_seconds = var.group_interval_seconds
  # group_wait_seconds - (optional) is a type of number
  group_wait_seconds = var.group_wait_seconds
  # inherited - (optional) is a type of bool
  inherited = var.inherited
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # repeat_interval_seconds - (optional) is a type of number
  repeat_interval_seconds = var.repeat_interval_seconds
  # severity - (optional) is a type of string
  severity = var.severity

  dynamic "metric_rule" {
    for_each = var.metric_rule
    content {
      # comparison - (optional) is a type of string
      comparison = metric_rule.value["comparison"]
      # description - (optional) is a type of string
      description = metric_rule.value["description"]
      # duration - (required) is a type of string
      duration = metric_rule.value["duration"]
      # expression - (required) is a type of string
      expression = metric_rule.value["expression"]
      # threshold_value - (required) is a type of number
      threshold_value = metric_rule.value["threshold_value"]
    }
  }

  dynamic "pod_rule" {
    for_each = var.pod_rule
    content {
      # condition - (optional) is a type of string
      condition = pod_rule.value["condition"]
      # pod_id - (required) is a type of string
      pod_id = pod_rule.value["pod_id"]
      # restart_interval_seconds - (optional) is a type of number
      restart_interval_seconds = pod_rule.value["restart_interval_seconds"]
      # restart_times - (optional) is a type of number
      restart_times = pod_rule.value["restart_times"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "workload_rule" {
    for_each = var.workload_rule
    content {
      # available_percentage - (optional) is a type of number
      available_percentage = workload_rule.value["available_percentage"]
      # selector - (optional) is a type of map of string
      selector = workload_rule.value["selector"]
      # workload_id - (optional) is a type of string
      workload_id = workload_rule.value["workload_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_project_alert_rule.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_project_alert_rule.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_project_alert_rule.this.labels
}

output "this" {
  value = rancher2_project_alert_rule.this
}
```

[top](#index)