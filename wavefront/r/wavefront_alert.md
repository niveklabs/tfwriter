# wavefront_alert

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_alert" {
  source = "./modules/wavefront/r/wavefront_alert"

  # additional_information - (optional) is a type of string
  additional_information = null
  # alert_type - (optional) is a type of string
  alert_type = null
  # can_modify - (optional) is a type of set of string
  can_modify = []
  # can_view - (optional) is a type of set of string
  can_view = []
  # condition - (optional) is a type of string
  condition = null
  # conditions - (optional) is a type of map of string
  conditions = {}
  # display_expression - (optional) is a type of string
  display_expression = null
  # minutes - (required) is a type of number
  minutes = null
  # name - (required) is a type of string
  name = null
  # notification_resend_frequency_minutes - (optional) is a type of number
  notification_resend_frequency_minutes = null
  # resolve_after_minutes - (optional) is a type of number
  resolve_after_minutes = null
  # severity - (optional) is a type of string
  severity = null
  # tags - (required) is a type of set of string
  tags = []
  # target - (optional) is a type of string
  target = null
  # threshold_targets - (optional) is a type of map of string
  threshold_targets = {}
}
```

[top](#index)

### Variables

```terraform
variable "additional_information" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "can_modify" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "can_view" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "condition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conditions" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "minutes" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_resend_frequency_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resolve_after_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(required)"
  type        = set(string)
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold_targets" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_alert" "this" {
  # additional_information - (optional) is a type of string
  additional_information = var.additional_information
  # alert_type - (optional) is a type of string
  alert_type = var.alert_type
  # can_modify - (optional) is a type of set of string
  can_modify = var.can_modify
  # can_view - (optional) is a type of set of string
  can_view = var.can_view
  # condition - (optional) is a type of string
  condition = var.condition
  # conditions - (optional) is a type of map of string
  conditions = var.conditions
  # display_expression - (optional) is a type of string
  display_expression = var.display_expression
  # minutes - (required) is a type of number
  minutes = var.minutes
  # name - (required) is a type of string
  name = var.name
  # notification_resend_frequency_minutes - (optional) is a type of number
  notification_resend_frequency_minutes = var.notification_resend_frequency_minutes
  # resolve_after_minutes - (optional) is a type of number
  resolve_after_minutes = var.resolve_after_minutes
  # severity - (optional) is a type of string
  severity = var.severity
  # tags - (required) is a type of set of string
  tags = var.tags
  # target - (optional) is a type of string
  target = var.target
  # threshold_targets - (optional) is a type of map of string
  threshold_targets = var.threshold_targets
}
```

[top](#index)

### Outputs

```terraform
output "can_modify" {
  description = "returns a set of string"
  value       = wavefront_alert.this.can_modify
}

output "id" {
  description = "returns a string"
  value       = wavefront_alert.this.id
}

output "severity" {
  description = "returns a string"
  value       = wavefront_alert.this.severity
}

output "this" {
  value = wavefront_alert.this
}
```

[top](#index)