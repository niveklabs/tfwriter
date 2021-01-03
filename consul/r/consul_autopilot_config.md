# consul_autopilot_config

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.10.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_autopilot_config" {
  source = "./modules/consul/r/consul_autopilot_config"

  # cleanup_dead_servers - (optional) is a type of bool
  cleanup_dead_servers = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # disable_upgrade_migration - (optional) is a type of bool
  disable_upgrade_migration = null
  # last_contact_threshold - (optional) is a type of string
  last_contact_threshold = null
  # max_trailing_logs - (optional) is a type of number
  max_trailing_logs = null
  # redundancy_zone_tag - (optional) is a type of string
  redundancy_zone_tag = null
  # server_stabilization_time - (optional) is a type of string
  server_stabilization_time = null
  # upgrade_version_tag - (optional) is a type of string
  upgrade_version_tag = null
}
```

[top](#index)

### Variables

```terraform
variable "cleanup_dead_servers" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_upgrade_migration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "last_contact_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_trailing_logs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "redundancy_zone_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_stabilization_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upgrade_version_tag" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_autopilot_config" "this" {
  cleanup_dead_servers      = var.cleanup_dead_servers
  datacenter                = var.datacenter
  disable_upgrade_migration = var.disable_upgrade_migration
  last_contact_threshold    = var.last_contact_threshold
  max_trailing_logs         = var.max_trailing_logs
  redundancy_zone_tag       = var.redundancy_zone_tag
  server_stabilization_time = var.server_stabilization_time
  upgrade_version_tag       = var.upgrade_version_tag
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_autopilot_config.this.id
}

output "this" {
  value = consul_autopilot_config.this
}
```

[top](#index)