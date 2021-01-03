# panos_panorama_nat_policy

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_nat_policy" {
  source = "./modules/panos/r/panos_panorama_nat_policy"

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
  # device_group - (optional) is a type of string
  device_group = null
  # disabled - (optional) is a type of bool
  disabled = null
  # name - (required) is a type of string
  name = null
  # negate_target - (optional) is a type of bool
  negate_target = null
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

  target = [{
    serial    = null
    vsys_list = []
  }]
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

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "negate_target" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "rulebase" {
  description = "(optional)"
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

variable "target" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      serial    = string
      vsys_list = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_nat_policy" "this" {
  dat_address                       = var.dat_address
  dat_dynamic_distribution          = var.dat_dynamic_distribution
  dat_port                          = var.dat_port
  dat_type                          = var.dat_type
  description                       = var.description
  destination_addresses             = var.destination_addresses
  destination_zone                  = var.destination_zone
  device_group                      = var.device_group
  disabled                          = var.disabled
  name                              = var.name
  negate_target                     = var.negate_target
  rulebase                          = var.rulebase
  sat_address_type                  = var.sat_address_type
  sat_fallback_interface            = var.sat_fallback_interface
  sat_fallback_ip_address           = var.sat_fallback_ip_address
  sat_fallback_ip_type              = var.sat_fallback_ip_type
  sat_fallback_translated_addresses = var.sat_fallback_translated_addresses
  sat_fallback_type                 = var.sat_fallback_type
  sat_interface                     = var.sat_interface
  sat_ip_address                    = var.sat_ip_address
  sat_static_bi_directional         = var.sat_static_bi_directional
  sat_static_translated_address     = var.sat_static_translated_address
  sat_translated_addresses          = var.sat_translated_addresses
  sat_type                          = var.sat_type
  service                           = var.service
  source_addresses                  = var.source_addresses
  source_zones                      = var.source_zones
  tags                              = var.tags
  to_interface                      = var.to_interface
  type                              = var.type

  dynamic "target" {
    for_each = var.target
    content {
      serial    = target.value["serial"]
      vsys_list = target.value["vsys_list"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_nat_policy.this.id
}

output "this" {
  value = panos_panorama_nat_policy.this
}
```

[top](#index)