# fortios_firewallshaper_trafficshaper

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
module "fortios_firewallshaper_trafficshaper" {
  source = "./modules/fortios/r/fortios_firewallshaper_trafficshaper"

  # bandwidth_unit - (optional) is a type of string
  bandwidth_unit = null
  # diffserv - (optional) is a type of string
  diffserv = null
  # diffservcode - (optional) is a type of string
  diffservcode = null
  # guaranteed_bandwidth - (optional) is a type of number
  guaranteed_bandwidth = null
  # maximum_bandwidth - (optional) is a type of number
  maximum_bandwidth = null
  # name - (optional) is a type of string
  name = null
  # per_policy - (optional) is a type of string
  per_policy = null
  # priority - (optional) is a type of string
  priority = null
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

variable "diffserv" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guaranteed_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallshaper_trafficshaper" "this" {
  bandwidth_unit       = var.bandwidth_unit
  diffserv             = var.diffserv
  diffservcode         = var.diffservcode
  guaranteed_bandwidth = var.guaranteed_bandwidth
  maximum_bandwidth    = var.maximum_bandwidth
  name                 = var.name
  per_policy           = var.per_policy
  priority             = var.priority
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_unit" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.bandwidth_unit
}

output "diffserv" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.diffserv
}

output "diffservcode" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.diffservcode
}

output "guaranteed_bandwidth" {
  description = "returns a number"
  value       = fortios_firewallshaper_trafficshaper.this.guaranteed_bandwidth
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.id
}

output "maximum_bandwidth" {
  description = "returns a number"
  value       = fortios_firewallshaper_trafficshaper.this.maximum_bandwidth
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.name
}

output "per_policy" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.per_policy
}

output "priority" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.priority
}

output "this" {
  value = fortios_firewallshaper_trafficshaper.this
}
```

[top](#index)