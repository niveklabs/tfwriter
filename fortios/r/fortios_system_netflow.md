# fortios_system_netflow

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_netflow" {
  source = "./modules/fortios/r/fortios_system_netflow"

  # active_flow_timeout - (optional) is a type of number
  active_flow_timeout = null
  # collector_ip - (optional) is a type of string
  collector_ip = null
  # collector_port - (optional) is a type of number
  collector_port = null
  # inactive_flow_timeout - (optional) is a type of number
  inactive_flow_timeout = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # template_tx_counter - (optional) is a type of number
  template_tx_counter = null
  # template_tx_timeout - (optional) is a type of number
  template_tx_timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "active_flow_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "collector_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "collector_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "inactive_flow_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tx_counter" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "template_tx_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_netflow" "this" {
  active_flow_timeout   = var.active_flow_timeout
  collector_ip          = var.collector_ip
  collector_port        = var.collector_port
  inactive_flow_timeout = var.inactive_flow_timeout
  source_ip             = var.source_ip
  template_tx_counter   = var.template_tx_counter
  template_tx_timeout   = var.template_tx_timeout
}
```

[top](#index)

### Outputs

```terraform
output "active_flow_timeout" {
  description = "returns a number"
  value       = fortios_system_netflow.this.active_flow_timeout
}

output "collector_ip" {
  description = "returns a string"
  value       = fortios_system_netflow.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = fortios_system_netflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = fortios_system_netflow.this.id
}

output "inactive_flow_timeout" {
  description = "returns a number"
  value       = fortios_system_netflow.this.inactive_flow_timeout
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_netflow.this.source_ip
}

output "template_tx_counter" {
  description = "returns a number"
  value       = fortios_system_netflow.this.template_tx_counter
}

output "template_tx_timeout" {
  description = "returns a number"
  value       = fortios_system_netflow.this.template_tx_timeout
}

output "this" {
  value = fortios_system_netflow.this
}
```

[top](#index)