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
    fortios = ">= 1.11.0"
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
  # dscp_marking_method - (optional) is a type of string
  dscp_marking_method = null
  # exceed_bandwidth - (optional) is a type of number
  exceed_bandwidth = null
  # exceed_class_id - (optional) is a type of number
  exceed_class_id = null
  # exceed_dscp - (optional) is a type of string
  exceed_dscp = null
  # guaranteed_bandwidth - (optional) is a type of number
  guaranteed_bandwidth = null
  # maximum_bandwidth - (optional) is a type of number
  maximum_bandwidth = null
  # maximum_dscp - (optional) is a type of string
  maximum_dscp = null
  # name - (optional) is a type of string
  name = null
  # overhead - (optional) is a type of number
  overhead = null
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

variable "dscp_marking_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exceed_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "exceed_class_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "exceed_dscp" {
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

variable "maximum_dscp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "overhead" {
  description = "(optional)"
  type        = number
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
  # bandwidth_unit - (optional) is a type of string
  bandwidth_unit = var.bandwidth_unit
  # diffserv - (optional) is a type of string
  diffserv = var.diffserv
  # diffservcode - (optional) is a type of string
  diffservcode = var.diffservcode
  # dscp_marking_method - (optional) is a type of string
  dscp_marking_method = var.dscp_marking_method
  # exceed_bandwidth - (optional) is a type of number
  exceed_bandwidth = var.exceed_bandwidth
  # exceed_class_id - (optional) is a type of number
  exceed_class_id = var.exceed_class_id
  # exceed_dscp - (optional) is a type of string
  exceed_dscp = var.exceed_dscp
  # guaranteed_bandwidth - (optional) is a type of number
  guaranteed_bandwidth = var.guaranteed_bandwidth
  # maximum_bandwidth - (optional) is a type of number
  maximum_bandwidth = var.maximum_bandwidth
  # maximum_dscp - (optional) is a type of string
  maximum_dscp = var.maximum_dscp
  # name - (optional) is a type of string
  name = var.name
  # overhead - (optional) is a type of number
  overhead = var.overhead
  # per_policy - (optional) is a type of string
  per_policy = var.per_policy
  # priority - (optional) is a type of string
  priority = var.priority
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

output "dscp_marking_method" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.dscp_marking_method
}

output "exceed_bandwidth" {
  description = "returns a number"
  value       = fortios_firewallshaper_trafficshaper.this.exceed_bandwidth
}

output "exceed_class_id" {
  description = "returns a number"
  value       = fortios_firewallshaper_trafficshaper.this.exceed_class_id
}

output "exceed_dscp" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.exceed_dscp
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

output "maximum_dscp" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.maximum_dscp
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallshaper_trafficshaper.this.name
}

output "overhead" {
  description = "returns a number"
  value       = fortios_firewallshaper_trafficshaper.this.overhead
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