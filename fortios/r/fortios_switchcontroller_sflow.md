# fortios_switchcontroller_sflow

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
module "fortios_switchcontroller_sflow" {
  source = "./modules/fortios/r/fortios_switchcontroller_sflow"

  # collector_ip - (required) is a type of string
  collector_ip = null
  # collector_port - (optional) is a type of number
  collector_port = null
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
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_sflow" "this" {
  collector_ip   = var.collector_ip
  collector_port = var.collector_port
}
```

[top](#index)

### Outputs

```terraform
output "collector_port" {
  description = "returns a number"
  value       = fortios_switchcontroller_sflow.this.collector_port
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_sflow.this.id
}

output "this" {
  value = fortios_switchcontroller_sflow.this
}
```

[top](#index)