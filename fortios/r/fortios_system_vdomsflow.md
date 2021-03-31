# fortios_system_vdomsflow

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_vdomsflow" {
  source = "./modules/fortios/r/fortios_system_vdomsflow"

  # collector_ip - (optional) is a type of string
  collector_ip = null
  # collector_port - (optional) is a type of number
  collector_port = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # vdom_sflow - (optional) is a type of string
  vdom_sflow = null
}
```

[top](#index)

### Variables

```terraform
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

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom_sflow" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdomsflow" "this" {
  collector_ip   = var.collector_ip
  collector_port = var.collector_port
  source_ip      = var.source_ip
  vdom_sflow     = var.vdom_sflow
}
```

[top](#index)

### Outputs

```terraform
output "collector_ip" {
  description = "returns a string"
  value       = fortios_system_vdomsflow.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = fortios_system_vdomsflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = fortios_system_vdomsflow.this.id
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_vdomsflow.this.source_ip
}

output "vdom_sflow" {
  description = "returns a string"
  value       = fortios_system_vdomsflow.this.vdom_sflow
}

output "this" {
  value = fortios_system_vdomsflow.this
}
```

[top](#index)