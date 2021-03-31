# fortios_system_nat64

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
module "fortios_system_nat64" {
  source = "./modules/fortios/r/fortios_system_nat64"

  # always_synthesize_aaaa_record - (optional) is a type of string
  always_synthesize_aaaa_record = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # generate_ipv6_fragment_header - (optional) is a type of string
  generate_ipv6_fragment_header = null
  # nat46_force_ipv4_packet_forwarding - (optional) is a type of string
  nat46_force_ipv4_packet_forwarding = null
  # nat64_prefix - (required) is a type of string
  nat64_prefix = null
  # secondary_prefix_status - (optional) is a type of string
  secondary_prefix_status = null
  # status - (optional) is a type of string
  status = null

  secondary_prefix = [{
    name         = null
    nat64_prefix = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "always_synthesize_aaaa_record" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "generate_ipv6_fragment_header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nat46_force_ipv4_packet_forwarding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nat64_prefix" {
  description = "(required)"
  type        = string
}

variable "secondary_prefix_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_prefix" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name         = string
      nat64_prefix = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_nat64" "this" {
  always_synthesize_aaaa_record      = var.always_synthesize_aaaa_record
  dynamic_sort_subtable              = var.dynamic_sort_subtable
  generate_ipv6_fragment_header      = var.generate_ipv6_fragment_header
  nat46_force_ipv4_packet_forwarding = var.nat46_force_ipv4_packet_forwarding
  nat64_prefix                       = var.nat64_prefix
  secondary_prefix_status            = var.secondary_prefix_status
  status                             = var.status

  dynamic "secondary_prefix" {
    for_each = var.secondary_prefix
    content {
      name         = secondary_prefix.value["name"]
      nat64_prefix = secondary_prefix.value["nat64_prefix"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "always_synthesize_aaaa_record" {
  description = "returns a string"
  value       = fortios_system_nat64.this.always_synthesize_aaaa_record
}

output "generate_ipv6_fragment_header" {
  description = "returns a string"
  value       = fortios_system_nat64.this.generate_ipv6_fragment_header
}

output "id" {
  description = "returns a string"
  value       = fortios_system_nat64.this.id
}

output "nat46_force_ipv4_packet_forwarding" {
  description = "returns a string"
  value       = fortios_system_nat64.this.nat46_force_ipv4_packet_forwarding
}

output "secondary_prefix_status" {
  description = "returns a string"
  value       = fortios_system_nat64.this.secondary_prefix_status
}

output "status" {
  description = "returns a string"
  value       = fortios_system_nat64.this.status
}

output "this" {
  value = fortios_system_nat64.this
}
```

[top](#index)