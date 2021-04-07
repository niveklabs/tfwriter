# oci_core_local_peering_gateway

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
module "oci_core_local_peering_gateway" {
  source = "./modules/oci/r/oci_core_local_peering_gateway"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # peer_id - (optional) is a type of string
  peer_id = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # vcn_id - (required) is a type of string
  vcn_id = null

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

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "peer_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcn_id" {
  description = "(required)"
  type        = string
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
resource "oci_core_local_peering_gateway" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # peer_id - (optional) is a type of string
  peer_id = var.peer_id
  # route_table_id - (optional) is a type of string
  route_table_id = var.route_table_id
  # vcn_id - (required) is a type of string
  vcn_id = var.vcn_id

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_local_peering_gateway.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_local_peering_gateway.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.id
}

output "is_cross_tenancy_peering" {
  description = "returns a bool"
  value       = oci_core_local_peering_gateway.this.is_cross_tenancy_peering
}

output "peer_advertised_cidr" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.peer_advertised_cidr
}

output "peer_advertised_cidr_details" {
  description = "returns a list of string"
  value       = oci_core_local_peering_gateway.this.peer_advertised_cidr_details
}

output "peering_status" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.peering_status
}

output "peering_status_details" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.peering_status_details
}

output "route_table_id" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.route_table_id
}

output "state" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_local_peering_gateway.this.time_created
}

output "this" {
  value = oci_core_local_peering_gateway.this
}
```

[top](#index)