# oci_core_virtual_circuit

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_virtual_circuit" {
  source = "./modules/oci/r/oci_core_virtual_circuit"

  # bandwidth_shape_name - (optional) is a type of string
  bandwidth_shape_name = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # customer_asn - (optional) is a type of string
  customer_asn = null
  # customer_bgp_asn - (optional) is a type of number
  customer_bgp_asn = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # gateway_id - (optional) is a type of string
  gateway_id = null
  # provider_service_id - (optional) is a type of string
  provider_service_id = null
  # provider_service_key_name - (optional) is a type of string
  provider_service_key_name = null
  # region - (optional) is a type of string
  region = null
  # type - (required) is a type of string
  type = null

  cross_connect_mappings = [{
    bgp_md5auth_key                         = null
    cross_connect_or_cross_connect_group_id = null
    customer_bgp_peering_ip                 = null
    customer_bgp_peering_ipv6               = null
    oracle_bgp_peering_ip                   = null
    oracle_bgp_peering_ipv6                 = null
    vlan                                    = null
  }]

  public_prefixes = [{
    cidr_block = null
  }]

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
variable "bandwidth_shape_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "customer_asn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customer_bgp_asn" {
  description = "(optional)"
  type        = number
  default     = null
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

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_service_key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "cross_connect_mappings" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bgp_md5auth_key                         = string
      cross_connect_or_cross_connect_group_id = string
      customer_bgp_peering_ip                 = string
      customer_bgp_peering_ipv6               = string
      oracle_bgp_peering_ip                   = string
      oracle_bgp_peering_ipv6                 = string
      vlan                                    = number
    }
  ))
  default = []
}

variable "public_prefixes" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cidr_block = string
    }
  ))
  default = []
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
resource "oci_core_virtual_circuit" "this" {
  bandwidth_shape_name      = var.bandwidth_shape_name
  compartment_id            = var.compartment_id
  customer_asn              = var.customer_asn
  customer_bgp_asn          = var.customer_bgp_asn
  defined_tags              = var.defined_tags
  display_name              = var.display_name
  freeform_tags             = var.freeform_tags
  gateway_id                = var.gateway_id
  provider_service_id       = var.provider_service_id
  provider_service_key_name = var.provider_service_key_name
  region                    = var.region
  type                      = var.type

  dynamic "cross_connect_mappings" {
    for_each = var.cross_connect_mappings
    content {
      bgp_md5auth_key                         = cross_connect_mappings.value["bgp_md5auth_key"]
      cross_connect_or_cross_connect_group_id = cross_connect_mappings.value["cross_connect_or_cross_connect_group_id"]
      customer_bgp_peering_ip                 = cross_connect_mappings.value["customer_bgp_peering_ip"]
      customer_bgp_peering_ipv6               = cross_connect_mappings.value["customer_bgp_peering_ipv6"]
      oracle_bgp_peering_ip                   = cross_connect_mappings.value["oracle_bgp_peering_ip"]
      oracle_bgp_peering_ipv6                 = cross_connect_mappings.value["oracle_bgp_peering_ipv6"]
      vlan                                    = cross_connect_mappings.value["vlan"]
    }
  }

  dynamic "public_prefixes" {
    for_each = var.public_prefixes
    content {
      cidr_block = public_prefixes.value["cidr_block"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_shape_name" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.bandwidth_shape_name
}

output "bgp_management" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.bgp_management
}

output "bgp_session_state" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.bgp_session_state
}

output "customer_asn" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.customer_asn
}

output "customer_bgp_asn" {
  description = "returns a number"
  value       = oci_core_virtual_circuit.this.customer_bgp_asn
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_virtual_circuit.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_virtual_circuit.this.freeform_tags
}

output "gateway_id" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.gateway_id
}

output "id" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.id
}

output "oracle_bgp_asn" {
  description = "returns a number"
  value       = oci_core_virtual_circuit.this.oracle_bgp_asn
}

output "provider_service_id" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.provider_service_id
}

output "provider_service_key_name" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.provider_service_key_name
}

output "provider_state" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.provider_state
}

output "reference_comment" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.reference_comment
}

output "region" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.region
}

output "service_type" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.service_type
}

output "state" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_virtual_circuit.this.time_created
}

output "this" {
  value = oci_core_virtual_circuit.this
}
```

[top](#index)