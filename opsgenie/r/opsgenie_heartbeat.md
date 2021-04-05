# opsgenie_heartbeat

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_heartbeat" {
  source = "./modules/opsgenie/r/opsgenie_heartbeat"

  # alert_message - (optional) is a type of string
  alert_message = null
  # alert_priority - (optional) is a type of string
  alert_priority = null
  # alert_tags - (optional) is a type of set of string
  alert_tags = []
  # description - (optional) is a type of string
  description = null
  # enabled - (required) is a type of bool
  enabled = null
  # interval - (required) is a type of number
  interval = null
  # interval_unit - (required) is a type of string
  interval_unit = null
  # name - (required) is a type of string
  name = null
  # owner_team_id - (optional) is a type of string
  owner_team_id = null
}
```

[top](#index)

### Variables

```terraform
variable "alert_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "interval" {
  description = "(required)"
  type        = number
}

variable "interval_unit" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner_team_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_heartbeat" "this" {
  alert_message  = var.alert_message
  alert_priority = var.alert_priority
  alert_tags     = var.alert_tags
  description    = var.description
  enabled        = var.enabled
  interval       = var.interval
  interval_unit  = var.interval_unit
  name           = var.name
  owner_team_id  = var.owner_team_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_heartbeat.this.id
}

output "this" {
  value = opsgenie_heartbeat.this
}
```

[top](#index)