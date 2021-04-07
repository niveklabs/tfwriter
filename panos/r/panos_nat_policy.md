# panos_nat_policy

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_nat_policy" {
  source = "./modules/panos/r/panos_nat_policy"

  # dat_address - (optional) is a type of string
  dat_address = null
  # dat_dynamic_distribution - (optional) is a type of string
  dat_dynamic_distribution = null
  # dat_port - (optional) is a type of number
  dat_port = null
  # dat_type - (optional) is a type of string
  dat_type = null
  # description - (optional) is a type of string
  description = null
  # destination_addresses - (required) is a type of list of string
  destination_addresses = []
  # destination_zone - (required) is a type of string
  destination_zone = null
  # disabled - (optional) is a type of bool
  disabled = null
  # name - (required) is a type of string
  name = null
  # rulebase - (optional) is a type of string
  rulebase = null
  # sat_address_type - (optional) is a type of string
  sat_address_type = null
  # sat_fallback_interface - (optional) is a type of string
  sat_fallback_interface = null
  # sat_fallback_ip_address - (optional) is a type of string
  sat_fallback_ip_address = null
  # sat_fallback_ip_type - (optional) is a type of string
  sat_fallback_ip_type = null
  # sat_fallback_translated_addresses - (optional) is a type of list of string
  sat_fallback_translated_addresses = []
  # sat_fallback_type - (optional) is a type of string
  sat_fallback_type = null
  # sat_interface - (optional) is a type of string
  sat_interface = null
  # sat_ip_address - (optional) is a type of string
  sat_ip_address = null
  # sat_static_bi_directional - (optional) is a type of bool
  sat_static_bi_directional = null
  # sat_static_translated_address - (optional) is a type of string
  sat_static_translated_address = null
  # sat_translated_addresses - (optional) is a type of list of string
  sat_translated_addresses = []
  # sat_type - (optional) is a type of string
  sat_type = null
  # service - (optional) is a type of string
  service = null
  # source_addresses - (required) is a type of list of string
  source_addresses = []
  # source_zones - (required) is a type of list of string
  source_zones = []
  # tags - (optional) is a type of list of string
  tags = []
  # to_interface - (optional) is a type of string
  to_interface = null
  # type - (optional) is a type of string
  type = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "dat_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dat_dynamic_distribution" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dat_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dat_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_addresses" {
  description = "(required)"
  type        = list(string)
}

variable "destination_zone" {
  description = "(required)"
  type        = string
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rulebase" {
  description = "(optional) - The Panorama rulebase"
  type        = string
  default     = null
}

variable "sat_address_type" {
  description = "(optional) - interface-address or translated-address"
  type        = string
  default     = null
}

variable "sat_fallback_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sat_fallback_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sat_fallback_ip_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sat_fallback_translated_addresses" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "sat_fallback_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sat_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sat_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sat_static_bi_directional" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sat_static_translated_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sat_translated_addresses" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "sat_type" {
  description = "(optional) - none (default), dynamic-ip-and-port, dynamic-ip, or static-ip"
  type        = string
  default     = null
}

variable "service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_addresses" {
  description = "(required)"
  type        = list(string)
}

variable "source_zones" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "to_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - NAT type (ipv4 default, nat64, or nptv6)"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional) - The vsys to put this object in (default: vsys1)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_nat_policy" "this" {
  # dat_address - (optional) is a type of string
  dat_address = var.dat_address
  # dat_dynamic_distribution - (optional) is a type of string
  dat_dynamic_distribution = var.dat_dynamic_distribution
  # dat_port - (optional) is a type of number
  dat_port = var.dat_port
  # dat_type - (optional) is a type of string
  dat_type = var.dat_type
  # description - (optional) is a type of string
  description = var.description
  # destination_addresses - (required) is a type of list of string
  destination_addresses = var.destination_addresses
  # destination_zone - (required) is a type of string
  destination_zone = var.destination_zone
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # name - (required) is a type of string
  name = var.name
  # rulebase - (optional) is a type of string
  rulebase = var.rulebase
  # sat_address_type - (optional) is a type of string
  sat_address_type = var.sat_address_type
  # sat_fallback_interface - (optional) is a type of string
  sat_fallback_interface = var.sat_fallback_interface
  # sat_fallback_ip_address - (optional) is a type of string
  sat_fallback_ip_address = var.sat_fallback_ip_address
  # sat_fallback_ip_type - (optional) is a type of string
  sat_fallback_ip_type = var.sat_fallback_ip_type
  # sat_fallback_translated_addresses - (optional) is a type of list of string
  sat_fallback_translated_addresses = var.sat_fallback_translated_addresses
  # sat_fallback_type - (optional) is a type of string
  sat_fallback_type = var.sat_fallback_type
  # sat_interface - (optional) is a type of string
  sat_interface = var.sat_interface
  # sat_ip_address - (optional) is a type of string
  sat_ip_address = var.sat_ip_address
  # sat_static_bi_directional - (optional) is a type of bool
  sat_static_bi_directional = var.sat_static_bi_directional
  # sat_static_translated_address - (optional) is a type of string
  sat_static_translated_address = var.sat_static_translated_address
  # sat_translated_addresses - (optional) is a type of list of string
  sat_translated_addresses = var.sat_translated_addresses
  # sat_type - (optional) is a type of string
  sat_type = var.sat_type
  # service - (optional) is a type of string
  service = var.service
  # source_addresses - (required) is a type of list of string
  source_addresses = var.source_addresses
  # source_zones - (required) is a type of list of string
  source_zones = var.source_zones
  # tags - (optional) is a type of list of string
  tags = var.tags
  # to_interface - (optional) is a type of string
  to_interface = var.to_interface
  # type - (optional) is a type of string
  type = var.type
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_nat_policy.this.id
}

output "rulebase" {
  description = "returns a string"
  value       = panos_nat_policy.this.rulebase
}

output "this" {
  value = panos_nat_policy.this
}
```

[top](#index)