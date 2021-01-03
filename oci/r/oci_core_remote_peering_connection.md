# oci_core_remote_peering_connection

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_remote_peering_connection" {
  source = "./modules/oci/r/oci_core_remote_peering_connection"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # drg_id - (required) is a type of string
  drg_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # peer_id - (optional) is a type of string
  peer_id = null
  # peer_region_name - (optional) is a type of string
  peer_region_name = null

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

variable "drg_id" {
  description = "(required)"
  type        = string
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

variable "peer_region_name" {
  description = "(optional)"
  type        = string
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
resource "oci_core_remote_peering_connection" "this" {
  compartment_id   = var.compartment_id
  defined_tags     = var.defined_tags
  display_name     = var.display_name
  drg_id           = var.drg_id
  freeform_tags    = var.freeform_tags
  peer_id          = var.peer_id
  peer_region_name = var.peer_region_name

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_remote_peering_connection.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_remote_peering_connection.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.id
}

output "is_cross_tenancy_peering" {
  description = "returns a bool"
  value       = oci_core_remote_peering_connection.this.is_cross_tenancy_peering
}

output "peer_id" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.peer_id
}

output "peer_region_name" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.peer_region_name
}

output "peer_tenancy_id" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.peer_tenancy_id
}

output "peering_status" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.peering_status
}

output "state" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_remote_peering_connection.this.time_created
}

output "this" {
  value = oci_core_remote_peering_connection.this
}
```

[top](#index)