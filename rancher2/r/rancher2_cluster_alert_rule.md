# rancher2_cluster_alert_rule

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
module "rancher2_cluster_alert_rule" {
  source = "./modules/rancher2/r/rancher2_cluster_alert_rule"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
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
  # repeat_interval_seconds - (optional) is a type of number
  repeat_interval_seconds = null
  # severity - (optional) is a type of string
  severity = null

  event_rule = [{
    event_type    = null
    resource_kind = null
  }]

  metric_rule = [{
    comparison      = null
    description     = null
    duration        = null
    expression      = null
    threshold_value = null
  }]

  node_rule = [{
    condition     = null
    cpu_threshold = null
    mem_threshold = null
    node_id       = null
    selector      = {}
  }]

  system_service_rule = [{
    condition = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "cluster_id" {
  description = "(required) - Alert rule cluster ID"
  type        = string
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

variable "event_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      event_type    = string
      resource_kind = string
    }
  ))
  default = []
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

variable "node_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      condition     = string
      cpu_threshold = number
      mem_threshold = number
      node_id       = string
      selector      = map(string)
    }
  ))
  default = []
}

variable "system_service_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      condition = string
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
```

[top](#index)

### Resource

```terraform
resource "rancher2_cluster_alert_rule" "this" {
  annotations             = var.annotations
  cluster_id              = var.cluster_id
  group_id                = var.group_id
  group_interval_seconds  = var.group_interval_seconds
  group_wait_seconds      = var.group_wait_seconds
  inherited               = var.inherited
  labels                  = var.labels
  name                    = var.name
  repeat_interval_seconds = var.repeat_interval_seconds
  severity                = var.severity

  dynamic "event_rule" {
    for_each = var.event_rule
    content {
      event_type    = event_rule.value["event_type"]
      resource_kind = event_rule.value["resource_kind"]
    }
  }

  dynamic "metric_rule" {
    for_each = var.metric_rule
    content {
      comparison      = metric_rule.value["comparison"]
      description     = metric_rule.value["description"]
      duration        = metric_rule.value["duration"]
      expression      = metric_rule.value["expression"]
      threshold_value = metric_rule.value["threshold_value"]
    }
  }

  dynamic "node_rule" {
    for_each = var.node_rule
    content {
      condition     = node_rule.value["condition"]
      cpu_threshold = node_rule.value["cpu_threshold"]
      mem_threshold = node_rule.value["mem_threshold"]
      node_id       = node_rule.value["node_id"]
      selector      = node_rule.value["selector"]
    }
  }

  dynamic "system_service_rule" {
    for_each = var.system_service_rule
    content {
      condition = system_service_rule.value["condition"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_cluster_alert_rule.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_cluster_alert_rule.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_cluster_alert_rule.this.labels
}

output "this" {
  value = rancher2_cluster_alert_rule.this
}
```

[top](#index)