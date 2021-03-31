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
    fortios = ">= 1.11.0"
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
  # ssl - (optional) is a type of string
  ssl = null
  # ssl_algorithm - (optional) is a type of string
  ssl_algorithm = null
  # ssl_cert - (optional) is a type of string
  ssl_cert = null
  # ssl_dh_bits - (optional) is a type of string
  ssl_dh_bits = null
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

variable "ssl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_dh_bits" {
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
  ssl                = var.ssl
  ssl_algorithm      = var.ssl_algorithm
  ssl_cert           = var.ssl_cert
  ssl_dh_bits        = var.ssl_dh_bits
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

output "ssl" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.ssl
}

output "ssl_algorithm" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.ssl_algorithm
}

output "ssl_cert" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.ssl_cert
}

output "ssl_dh_bits" {
  description = "returns a string"
  value       = fortios_ftpproxy_explicit.this.ssl_dh_bits
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