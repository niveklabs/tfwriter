# rancher2_project_alert_group

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
module "rancher2_project_alert_group" {
  source = "./modules/rancher2/r/rancher2_project_alert_group"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # group_interval_seconds - (optional) is a type of number
  group_interval_seconds = null
  # group_wait_seconds - (optional) is a type of number
  group_wait_seconds = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # repeat_interval_seconds - (optional) is a type of number
  repeat_interval_seconds = null

  recipients = [{
    default_recipient = null
    notifier_id       = null
    notifier_type     = null
    recipient         = null
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

variable "description" {
  description = "(optional) - Alert group description"
  type        = string
  default     = null
}

variable "group_interval_seconds" {
  description = "(optional) - Alert group interval seconds"
  type        = number
  default     = null
}

variable "group_wait_seconds" {
  description = "(optional) - Alert group wait seconds"
  type        = number
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Alert group name"
  type        = string
}

variable "project_id" {
  description = "(required) - Alert group Project ID"
  type        = string
}

variable "repeat_interval_seconds" {
  description = "(optional) - Alert group repeat interval seconds"
  type        = number
  default     = null
}

variable "recipients" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default_recipient = bool
      notifier_id       = string
      notifier_type     = string
      recipient         = string
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
resource "rancher2_project_alert_group" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # description - (optional) is a type of string
  description = var.description
  # group_interval_seconds - (optional) is a type of number
  group_interval_seconds = var.group_interval_seconds
  # group_wait_seconds - (optional) is a type of number
  group_wait_seconds = var.group_wait_seconds
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # repeat_interval_seconds - (optional) is a type of number
  repeat_interval_seconds = var.repeat_interval_seconds

  dynamic "recipients" {
    for_each = var.recipients
    content {
      # default_recipient - (optional) is a type of bool
      default_recipient = recipients.value["default_recipient"]
      # notifier_id - (required) is a type of string
      notifier_id = recipients.value["notifier_id"]
      # recipient - (optional) is a type of string
      recipient = recipients.value["recipient"]
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

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_project_alert_group.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_project_alert_group.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_project_alert_group.this.labels
}

output "this" {
  value = rancher2_project_alert_group.this
}
```

[top](#index)