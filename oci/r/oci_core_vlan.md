# oci_core_vlan

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
module "oci_core_vlan" {
  source = "./modules/oci/r/oci_core_vlan"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # vcn_id - (required) is a type of string
  vcn_id = null
  # vlan_tag - (optional) is a type of number
  vlan_tag = null

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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "cidr_block" {
  description = "(required)"
  type        = string
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

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
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

variable "vlan_tag" {
  description = "(optional)"
  type        = number
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
resource "oci_core_vlan" "this" {
  availability_domain = var.availability_domain
  cidr_block          = var.cidr_block
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags
  nsg_ids             = var.nsg_ids
  route_table_id      = var.route_table_id
  vcn_id              = var.vcn_id
  vlan_tag            = var.vlan_tag

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
  value       = oci_core_vlan.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_vlan.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_vlan.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_vlan.this.id
}

output "nsg_ids" {
  description = "returns a set of string"
  value       = oci_core_vlan.this.nsg_ids
}

output "route_table_id" {
  description = "returns a string"
  value       = oci_core_vlan.this.route_table_id
}

output "state" {
  description = "returns a string"
  value       = oci_core_vlan.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_vlan.this.time_created
}

output "vlan_tag" {
  description = "returns a number"
  value       = oci_core_vlan.this.vlan_tag
}

output "this" {
  value = oci_core_vlan.this
}
```

[top](#index)