# fortios_firewallshaper_peripshaper

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
module "fortios_firewallshaper_peripshaper" {
  source = "./modules/fortios/r/fortios_firewallshaper_peripshaper"

  # bandwidth_unit - (optional) is a type of string
  bandwidth_unit = null
  # diffserv_forward - (optional) is a type of string
  diffserv_forward = null
  # diffserv_reverse - (optional) is a type of string
  diffserv_reverse = null
  # diffservcode_forward - (optional) is a type of string
  diffservcode_forward = null
  # diffservcode_rev - (optional) is a type of string
  diffservcode_rev = null
  # max_bandwidth - (optional) is a type of number
  max_bandwidth = null
  # max_concurrent_session - (optional) is a type of number
  max_concurrent_session = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffserv_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffserv_reverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode_rev" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_concurrent_session" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallshaper_peripshaper" "this" {
  bandwidth_unit         = var.bandwidth_unit
  diffserv_forward       = var.diffserv_forward
  diffserv_reverse       = var.diffserv_reverse
  diffservcode_forward   = var.diffservcode_forward
  diffservcode_rev       = var.diffservcode_rev
  max_bandwidth          = var.max_bandwidth
  max_concurrent_session = var.max_concurrent_session
  name                   = var.name
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_unit" {
  description = "returns a string"
  value       = fortios_firewallshaper_peripshaper.this.bandwidth_unit
}

output "diffserv_forward" {
  description = "returns a string"
  value       = fortios_firewallshaper_peripshaper.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = fortios_firewallshaper_peripshaper.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = fortios_firewallshaper_peripshaper.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = fortios_firewallshaper_peripshaper.this.diffservcode_rev
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallshaper_peripshaper.this.id
}

output "max_bandwidth" {
  description = "returns a number"
  value       = fortios_firewallshaper_peripshaper.this.max_bandwidth
}

output "max_concurrent_session" {
  description = "returns a number"
  value       = fortios_firewallshaper_peripshaper.this.max_concurrent_session
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallshaper_peripshaper.this.name
}

output "this" {
  value = fortios_firewallshaper_peripshaper.this
}
```

[top](#index)