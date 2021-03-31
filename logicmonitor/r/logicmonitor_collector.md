# logicmonitor_collector

[back](../logicmonitor.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    logicmonitor = ">= 1.3.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "logicmonitor_collector" {
  source = "./modules/logicmonitor/r/logicmonitor_collector"

  # backup_collector_id - (optional) is a type of number
  backup_collector_id = null
  # collector_group_id - (optional) is a type of number
  collector_group_id = null
  # description - (optional) is a type of string
  description = null
  # enable_collector_device_failover - (optional) is a type of bool
  enable_collector_device_failover = null
  # enable_failback - (optional) is a type of bool
  enable_failback = null
  # escalation_chain_id - (optional) is a type of number
  escalation_chain_id = null
  # properties - (optional) is a type of map of string
  properties = {}
  # resend_interval - (optional) is a type of number
  resend_interval = null
  # suppress_alert_clear - (optional) is a type of bool
  suppress_alert_clear = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_collector_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "collector_group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_collector_device_failover" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_failback" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "escalation_chain_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resend_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "suppress_alert_clear" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "logicmonitor_collector" "this" {
  backup_collector_id              = var.backup_collector_id
  collector_group_id               = var.collector_group_id
  description                      = var.description
  enable_collector_device_failover = var.enable_collector_device_failover
  enable_failback                  = var.enable_failback
  escalation_chain_id              = var.escalation_chain_id
  properties                       = var.properties
  resend_interval                  = var.resend_interval
  suppress_alert_clear             = var.suppress_alert_clear
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = logicmonitor_collector.this.id
}

output "this" {
  value = logicmonitor_collector.this
}
```

[top](#index)