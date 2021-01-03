# fortios_system_vdomnetflow

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
module "fortios_system_vdomnetflow" {
  source = "./modules/fortios/r/fortios_system_vdomnetflow"

  # collector_ip - (optional) is a type of string
  collector_ip = null
  # collector_port - (optional) is a type of number
  collector_port = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # vdom_netflow - (optional) is a type of string
  vdom_netflow = null
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

variable "vdom_netflow" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdomnetflow" "this" {
  collector_ip   = var.collector_ip
  collector_port = var.collector_port
  source_ip      = var.source_ip
  vdom_netflow   = var.vdom_netflow
}
```

[top](#index)

### Outputs

```terraform
output "collector_ip" {
  description = "returns a string"
  value       = fortios_system_vdomnetflow.this.collector_ip
}

output "collector_port" {
  description = "returns a number"
  value       = fortios_system_vdomnetflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = fortios_system_vdomnetflow.this.id
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_vdomnetflow.this.source_ip
}

output "vdom_netflow" {
  description = "returns a string"
  value       = fortios_system_vdomnetflow.this.vdom_netflow
}

output "this" {
  value = fortios_system_vdomnetflow.this
}
```

[top](#index)