# fortios_webfilter_fortiguard

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
module "fortios_webfilter_fortiguard" {
  source = "./modules/fortios/r/fortios_webfilter_fortiguard"

  # cache_mem_percent - (optional) is a type of number
  cache_mem_percent = null
  # cache_mode - (optional) is a type of string
  cache_mode = null
  # cache_prefix_match - (optional) is a type of string
  cache_prefix_match = null
  # close_ports - (optional) is a type of string
  close_ports = null
  # ovrd_auth_https - (optional) is a type of string
  ovrd_auth_https = null
  # ovrd_auth_port - (optional) is a type of number
  ovrd_auth_port = null
  # ovrd_auth_port_http - (optional) is a type of number
  ovrd_auth_port_http = null
  # ovrd_auth_port_https - (optional) is a type of number
  ovrd_auth_port_https = null
  # ovrd_auth_port_https_flow - (optional) is a type of number
  ovrd_auth_port_https_flow = null
  # ovrd_auth_port_warning - (optional) is a type of number
  ovrd_auth_port_warning = null
  # request_packet_size_limit - (optional) is a type of number
  request_packet_size_limit = null
  # warn_auth_https - (optional) is a type of string
  warn_auth_https = null
}
```

[top](#index)

### Variables

```terraform
variable "cache_mem_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cache_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_prefix_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "close_ports" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ovrd_auth_https" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ovrd_auth_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ovrd_auth_port_http" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ovrd_auth_port_https" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ovrd_auth_port_https_flow" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ovrd_auth_port_warning" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "request_packet_size_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "warn_auth_https" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_fortiguard" "this" {
  cache_mem_percent         = var.cache_mem_percent
  cache_mode                = var.cache_mode
  cache_prefix_match        = var.cache_prefix_match
  close_ports               = var.close_ports
  ovrd_auth_https           = var.ovrd_auth_https
  ovrd_auth_port            = var.ovrd_auth_port
  ovrd_auth_port_http       = var.ovrd_auth_port_http
  ovrd_auth_port_https      = var.ovrd_auth_port_https
  ovrd_auth_port_https_flow = var.ovrd_auth_port_https_flow
  ovrd_auth_port_warning    = var.ovrd_auth_port_warning
  request_packet_size_limit = var.request_packet_size_limit
  warn_auth_https           = var.warn_auth_https
}
```

[top](#index)

### Outputs

```terraform
output "cache_mem_percent" {
  description = "returns a number"
  value       = fortios_webfilter_fortiguard.this.cache_mem_percent
}

output "cache_mode" {
  description = "returns a string"
  value       = fortios_webfilter_fortiguard.this.cache_mode
}

output "cache_prefix_match" {
  description = "returns a string"
  value       = fortios_webfilter_fortiguard.this.cache_prefix_match
}

output "close_ports" {
  description = "returns a string"
  value       = fortios_webfilter_fortiguard.this.close_ports
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_fortiguard.this.id
}

output "ovrd_auth_https" {
  description = "returns a string"
  value       = fortios_webfilter_fortiguard.this.ovrd_auth_https
}

output "ovrd_auth_port" {
  description = "returns a number"
  value       = fortios_webfilter_fortiguard.this.ovrd_auth_port
}

output "ovrd_auth_port_http" {
  description = "returns a number"
  value       = fortios_webfilter_fortiguard.this.ovrd_auth_port_http
}

output "ovrd_auth_port_https" {
  description = "returns a number"
  value       = fortios_webfilter_fortiguard.this.ovrd_auth_port_https
}

output "ovrd_auth_port_https_flow" {
  description = "returns a number"
  value       = fortios_webfilter_fortiguard.this.ovrd_auth_port_https_flow
}

output "ovrd_auth_port_warning" {
  description = "returns a number"
  value       = fortios_webfilter_fortiguard.this.ovrd_auth_port_warning
}

output "request_packet_size_limit" {
  description = "returns a number"
  value       = fortios_webfilter_fortiguard.this.request_packet_size_limit
}

output "warn_auth_https" {
  description = "returns a string"
  value       = fortios_webfilter_fortiguard.this.warn_auth_https
}

output "this" {
  value = fortios_webfilter_fortiguard.this
}
```

[top](#index)