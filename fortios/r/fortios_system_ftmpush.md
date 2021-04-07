# fortios_system_ftmpush

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
module "fortios_system_ftmpush" {
  source = "./modules/fortios/r/fortios_system_ftmpush"

  # server_cert - (optional) is a type of string
  server_cert = null
  # server_ip - (optional) is a type of string
  server_ip = null
  # server_port - (optional) is a type of number
  server_port = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "server_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ftmpush" "this" {
  # server_cert - (optional) is a type of string
  server_cert = var.server_cert
  # server_ip - (optional) is a type of string
  server_ip = var.server_ip
  # server_port - (optional) is a type of number
  server_port = var.server_port
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_ftmpush.this.id
}

output "server_cert" {
  description = "returns a string"
  value       = fortios_system_ftmpush.this.server_cert
}

output "server_ip" {
  description = "returns a string"
  value       = fortios_system_ftmpush.this.server_ip
}

output "server_port" {
  description = "returns a number"
  value       = fortios_system_ftmpush.this.server_port
}

output "status" {
  description = "returns a string"
  value       = fortios_system_ftmpush.this.status
}

output "this" {
  value = fortios_system_ftmpush.this
}
```

[top](#index)