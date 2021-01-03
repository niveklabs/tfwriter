# fortios_ftpproxy_explicit

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
module "fortios_ftpproxy_explicit" {
  source = "./modules/fortios/r/fortios_ftpproxy_explicit"

  # incoming_ip - (optional) is a type of string
  incoming_ip = null
  # incoming_port - (optional) is a type of string
  incoming_port = null
  # outgoing_ip - (optional) is a type of string
  outgoing_ip = null
  # sec_default_action - (optional) is a type of string
  sec_default_action = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "incoming_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "incoming_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outgoing_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sec_default_action" {
  description = "(optional)"
  type        = string
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
resource "fortios_ftpproxy_explicit" "this" {
  incoming_ip        = var.incoming_ip
  incoming_port      = var.incoming_port
  outgoing_ip        = var.outgoing_ip
  sec_default_action = var.sec_default_action
  status             = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.id
}

output "incoming_ip" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.incoming_ip
}

output "incoming_port" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.incoming_port
}

output "outgoing_ip" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.outgoing_ip
}

output "sec_default_action" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.sec_default_action
}

output "status" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.status
}

output "this" {
  value = fortios_ftpproxy_explicit.this
}
```

[top](#index)