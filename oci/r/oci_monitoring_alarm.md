# oci_monitoring_alarm

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_monitoring_alarm" {
  source = "./modules/oci/r/oci_monitoring_alarm"

  # body - (optional) is a type of string
  body = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # destinations - (required) is a type of list of string
  destinations = []
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_enabled - (required) is a type of bool
  is_enabled = null
  # metric_compartment_id - (required) is a type of string
  metric_compartment_id = null
  # metric_compartment_id_in_subtree - (optional) is a type of bool
  metric_compartment_id_in_subtree = null
  # namespace - (required) is a type of string
  namespace = null
  # pending_duration - (optional) is a type of string
  pending_duration = null
  # query - (required) is a type of string
  query = null
  # repeat_notification_duration - (optional) is a type of string
  repeat_notification_duration = null
  # resolution - (optional) is a type of string
  resolution = null
  # resource_group - (optional) is a type of string
  resource_group = null
  # severity - (required) is a type of string
  severity = null

  suppression = [{
    description         = null
    time_suppress_from  = null
    time_suppress_until = null
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
variable "body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "destinations" {
  description = "(required)"
  type        = list(string)
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_enabled" {
  description = "(required)"
  type        = bool
}

variable "metric_compartment_id" {
  description = "(required)"
  type        = string
}

variable "metric_compartment_id_in_subtree" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "pending_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query" {
  description = "(required)"
  type        = string
}

variable "repeat_notification_duration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolution" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
  description = "(required)"
  type        = string
}

variable "suppression" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description         = string
      time_suppress_from  = string
      time_suppress_until = string
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
resource "oci_monitoring_alarm" "this" {
  body                             = var.body
  compartment_id                   = var.compartment_id
  defined_tags                     = var.defined_tags
  destinations                     = var.destinations
  display_name                     = var.display_name
  freeform_tags                    = var.freeform_tags
  is_enabled                       = var.is_enabled
  metric_compartment_id            = var.metric_compartment_id
  metric_compartment_id_in_subtree = var.metric_compartment_id_in_subtree
  namespace                        = var.namespace
  pending_duration                 = var.pending_duration
  query                            = var.query
  repeat_notification_duration     = var.repeat_notification_duration
  resolution                       = var.resolution
  resource_group                   = var.resource_group
  severity                         = var.severity

  dynamic "suppression" {
    for_each = var.suppression
    content {
      description         = suppression.value["description"]
      time_suppress_from  = suppression.value["time_suppress_from"]
      time_suppress_until = suppression.value["time_suppress_until"]
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
output "body" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.body
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_monitoring_alarm.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_monitoring_alarm.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.id
}

output "metric_compartment_id_in_subtree" {
  description = "returns a bool"
  value       = oci_monitoring_alarm.this.metric_compartment_id_in_subtree
}

output "pending_duration" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.pending_duration
}

output "repeat_notification_duration" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.repeat_notification_duration
}

output "resolution" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.resolution
}

output "resource_group" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.resource_group
}

output "state" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_monitoring_alarm.this.time_updated
}

output "this" {
  value = oci_monitoring_alarm.this
}
```

[top](#index)