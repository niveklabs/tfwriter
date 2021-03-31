# fortios_firewall_ipv6ehfilter

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
module "fortios_firewall_ipv6ehfilter" {
  source = "./modules/fortios/r/fortios_firewall_ipv6ehfilter"

  # auth - (optional) is a type of string
  auth = null
  # dest_opt - (optional) is a type of string
  dest_opt = null
  # fragment - (optional) is a type of string
  fragment = null
  # hdopt_type - (optional) is a type of number
  hdopt_type = null
  # hop_opt - (optional) is a type of string
  hop_opt = null
  # no_next - (optional) is a type of string
  no_next = null
  # routing - (optional) is a type of string
  routing = null
  # routing_type - (optional) is a type of number
  routing_type = null
}
```

[top](#index)

### Variables

```terraform
variable "auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dest_opt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fragment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hdopt_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hop_opt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "no_next" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "routing_type" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_ipv6ehfilter" "this" {
  auth         = var.auth
  dest_opt     = var.dest_opt
  fragment     = var.fragment
  hdopt_type   = var.hdopt_type
  hop_opt      = var.hop_opt
  no_next      = var.no_next
  routing      = var.routing
  routing_type = var.routing_type
}
```

[top](#index)

### Outputs

```terraform
output "auth" {
  description = "returns a string"
  value       = fortios_firewall_ipv6ehfilter.this.auth
}

output "dest_opt" {
  description = "returns a string"
  value       = fortios_firewall_ipv6ehfilter.this.dest_opt
}

output "fragment" {
  description = "returns a string"
  value       = fortios_firewall_ipv6ehfilter.this.fragment
}

output "hdopt_type" {
  description = "returns a number"
  value       = fortios_firewall_ipv6ehfilter.this.hdopt_type
}

output "hop_opt" {
  description = "returns a string"
  value       = fortios_firewall_ipv6ehfilter.this.hop_opt
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_ipv6ehfilter.this.id
}

output "no_next" {
  description = "returns a string"
  value       = fortios_firewall_ipv6ehfilter.this.no_next
}

output "routing" {
  description = "returns a string"
  value       = fortios_firewall_ipv6ehfilter.this.routing
}

output "routing_type" {
  description = "returns a number"
  value       = fortios_firewall_ipv6ehfilter.this.routing_type
}

output "this" {
  value = fortios_firewall_ipv6ehfilter.this
}
```

[top](#index)