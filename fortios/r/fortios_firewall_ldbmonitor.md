# fortios_firewall_ldbmonitor

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
module "fortios_firewall_ldbmonitor" {
  source = "./modules/fortios/r/fortios_firewall_ldbmonitor"

  # http_get - (optional) is a type of string
  http_get = null
  # http_match - (optional) is a type of string
  http_match = null
  # http_max_redirects - (optional) is a type of number
  http_max_redirects = null
  # interval - (optional) is a type of number
  interval = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # retry - (optional) is a type of number
  retry = null
  # src_ip - (optional) is a type of string
  src_ip = null
  # timeout - (optional) is a type of number
  timeout = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "http_get" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_match" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_max_redirects" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interval" {
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
  description = "(optional)"
  type        = number
  default     = null
}

variable "retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "src_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_ldbmonitor" "this" {
  # http_get - (optional) is a type of string
  http_get = var.http_get
  # http_match - (optional) is a type of string
  http_match = var.http_match
  # http_max_redirects - (optional) is a type of number
  http_max_redirects = var.http_max_redirects
  # interval - (optional) is a type of number
  interval = var.interval
  # name - (optional) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # retry - (optional) is a type of number
  retry = var.retry
  # src_ip - (optional) is a type of string
  src_ip = var.src_ip
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "http_get" {
  description = "returns a string"
  value       = fortios_firewall_ldbmonitor.this.http_get
}

output "http_match" {
  description = "returns a string"
  value       = fortios_firewall_ldbmonitor.this.http_match
}

output "http_max_redirects" {
  description = "returns a number"
  value       = fortios_firewall_ldbmonitor.this.http_max_redirects
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_ldbmonitor.this.id
}

output "interval" {
  description = "returns a number"
  value       = fortios_firewall_ldbmonitor.this.interval
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_ldbmonitor.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_firewall_ldbmonitor.this.port
}

output "retry" {
  description = "returns a number"
  value       = fortios_firewall_ldbmonitor.this.retry
}

output "src_ip" {
  description = "returns a string"
  value       = fortios_firewall_ldbmonitor.this.src_ip
}

output "timeout" {
  description = "returns a number"
  value       = fortios_firewall_ldbmonitor.this.timeout
}

output "this" {
  value = fortios_firewall_ldbmonitor.this
}
```

[top](#index)