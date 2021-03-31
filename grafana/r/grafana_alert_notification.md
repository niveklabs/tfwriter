# grafana_alert_notification

[back](../grafana.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    grafana = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "grafana_alert_notification" {
  source = "./modules/grafana/r/grafana_alert_notification"

  # disable_resolve_message - (optional) is a type of bool
  disable_resolve_message = null
  # frequency - (optional) is a type of string
  frequency = null
  # is_default - (optional) is a type of bool
  is_default = null
  # name - (required) is a type of string
  name = null
  # send_reminder - (optional) is a type of bool
  send_reminder = null
  # settings - (optional) is a type of map of string
  settings = {}
  # type - (required) is a type of string
  type = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "disable_resolve_message" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "send_reminder" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "settings" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "uid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "grafana_alert_notification" "this" {
  disable_resolve_message = var.disable_resolve_message
  frequency               = var.frequency
  is_default              = var.is_default
  name                    = var.name
  send_reminder           = var.send_reminder
  settings                = var.settings
  type                    = var.type
  uid                     = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_alert_notification.this.id
}

output "uid" {
  description = "returns a string"
  value       = grafana_alert_notification.this.uid
}

output "this" {
  value = grafana_alert_notification.this
}
```

[top](#index)