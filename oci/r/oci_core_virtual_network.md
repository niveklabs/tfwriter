# oci_core_virtual_network

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_virtual_network" {
  source = "./modules/oci/r/oci_core_virtual_network"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # cidr_blocks - (optional) is a type of list of string
  cidr_blocks = []
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # dns_label - (optional) is a type of string
  dns_label = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # ipv6cidr_block - (optional) is a type of string
  ipv6cidr_block = null
  # is_ipv6enabled - (optional) is a type of bool
  is_ipv6enabled = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cidr_blocks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ipv6cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_ipv6enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_core_virtual_network" "this" {
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # cidr_blocks - (optional) is a type of list of string
  cidr_blocks = var.cidr_blocks
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # dns_label - (optional) is a type of string
  dns_label = var.dns_label
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # ipv6cidr_block - (optional) is a type of string
  ipv6cidr_block = var.ipv6cidr_block
  # is_ipv6enabled - (optional) is a type of bool
  is_ipv6enabled = var.is_ipv6enabled

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cidr_block" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.cidr_block
}

output "cidr_blocks" {
  description = "returns a list of string"
  value       = oci_core_virtual_network.this.cidr_blocks
}

output "default_dhcp_options_id" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.default_dhcp_options_id
}

output "default_route_table_id" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.default_route_table_id
}

output "default_security_list_id" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.default_security_list_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_virtual_network.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.display_name
}

output "dns_label" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.dns_label
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_virtual_network.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.id
}

output "ipv6cidr_block" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.ipv6cidr_block
}

output "ipv6public_cidr_block" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.ipv6public_cidr_block
}

output "is_ipv6enabled" {
  description = "returns a bool"
  value       = oci_core_virtual_network.this.is_ipv6enabled
}

output "state" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.time_created
}

output "vcn_domain_name" {
  description = "returns a string"
  value       = oci_core_virtual_network.this.vcn_domain_name
}

output "this" {
  value = oci_core_virtual_network.this
}
```

[top](#index)