# fortios_system_sflow

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
module "fortios_system_sflow" {
  source = "./modules/fortios/r/fortios_system_sflow"

  # collector_ip - (required) is a type of string
  collector_ip = null
  # collector_port - (optional) is a type of number
  collector_port = null
  # source_ip - (optional) is a type of string
  source_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "collector_ip" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "fortios_system_sflow" "this" {
  collector_ip   = var.collector_ip
  collector_port = var.collector_port
  source_ip      = var.source_ip
}
```

[top](#index)

### Outputs

```terraform
output "collector_port" {
  description = "returns a number"
  value       = fortios_system_sflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = fortios_system_sflow.this.id
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_sflow.this.source_ip
}

output "this" {
  value = fortios_system_sflow.this
}
```

[top](#index)