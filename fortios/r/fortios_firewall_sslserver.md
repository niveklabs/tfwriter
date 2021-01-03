# fortios_firewall_sslserver

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
module "fortios_firewall_sslserver" {
  source = "./modules/fortios/r/fortios_firewall_sslserver"

  # add_header_x_forwarded_proto - (optional) is a type of string
  add_header_x_forwarded_proto = null
  # ip - (required) is a type of string
  ip = null
  # mapped_port - (optional) is a type of number
  mapped_port = null
  # name - (optional) is a type of string
  name = null
  # port - (required) is a type of number
  port = null
  # ssl_algorithm - (optional) is a type of string
  ssl_algorithm = null
  # ssl_cert - (required) is a type of string
  ssl_cert = null
  # ssl_client_renegotiation - (optional) is a type of string
  ssl_client_renegotiation = null
  # ssl_dh_bits - (optional) is a type of string
  ssl_dh_bits = null
  # ssl_max_version - (optional) is a type of string
  ssl_max_version = null
  # ssl_min_version - (optional) is a type of string
  ssl_min_version = null
  # ssl_mode - (optional) is a type of string
  ssl_mode = null
  # ssl_send_empty_frags - (optional) is a type of string
  ssl_send_empty_frags = null
  # url_rewrite - (optional) is a type of string
  url_rewrite = null
}
```

[top](#index)

### Variables

```terraform
variable "add_header_x_forwarded_proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "mapped_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "ssl_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_cert" {
  description = "(required)"
  type        = string
}

variable "ssl_client_renegotiation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_dh_bits" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_max_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_send_empty_frags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_rewrite" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_sslserver" "this" {
  add_header_x_forwarded_proto = var.add_header_x_forwarded_proto
  ip                           = var.ip
  mapped_port                  = var.mapped_port
  name                         = var.name
  port                         = var.port
  ssl_algorithm                = var.ssl_algorithm
  ssl_cert                     = var.ssl_cert
  ssl_client_renegotiation     = var.ssl_client_renegotiation
  ssl_dh_bits                  = var.ssl_dh_bits
  ssl_max_version              = var.ssl_max_version
  ssl_min_version              = var.ssl_min_version
  ssl_mode                     = var.ssl_mode
  ssl_send_empty_frags         = var.ssl_send_empty_frags
  url_rewrite                  = var.url_rewrite
}
```

[top](#index)

### Outputs

```terraform
output "add_header_x_forwarded_proto" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.add_header_x_forwarded_proto
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.id
}

output "mapped_port" {
  description = "returns a number"
  value       = fortios_firewall_sslserver.this.mapped_port
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.name
}

output "ssl_algorithm" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.ssl_algorithm
}

output "ssl_client_renegotiation" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.ssl_client_renegotiation
}

output "ssl_dh_bits" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.ssl_dh_bits
}

output "ssl_max_version" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.ssl_max_version
}

output "ssl_min_version" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.ssl_min_version
}

output "ssl_mode" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.ssl_mode
}

output "ssl_send_empty_frags" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.ssl_send_empty_frags
}

output "url_rewrite" {
  description = "returns a string"
  value       = fortios_firewall_sslserver.this.url_rewrite
}

output "this" {
  value = fortios_firewall_sslserver.this
}
```

[top](#index)