# oci_core_route_table

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
module "oci_core_route_table" {
  source = "./modules/oci/r/oci_core_route_table"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # vcn_id - (required) is a type of string
  vcn_id = null

  route_rules = [{
    cidr_block        = null
    description       = null
    destination       = null
    destination_type  = null
    network_entity_id = null
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

variable "vcn_id" {
  description = "(required)"
  type        = string
}

variable "route_rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cidr_block        = string
      description       = string
      destination       = string
      destination_type  = string
      network_entity_id = string
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
resource "oci_core_route_table" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # vcn_id - (required) is a type of string
  vcn_id = var.vcn_id

  dynamic "route_rules" {
    for_each = var.route_rules
    content {
      # cidr_block - (optional) is a type of string
      cidr_block = route_rules.value["cidr_block"]
      # description - (optional) is a type of string
      description = route_rules.value["description"]
      # destination - (optional) is a type of string
      destination = route_rules.value["destination"]
      # destination_type - (optional) is a type of string
      destination_type = route_rules.value["destination_type"]
      # network_entity_id - (required) is a type of string
      network_entity_id = route_rules.value["network_entity_id"]
    }
  }

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
  value       = oci_core_route_table.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_route_table.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_route_table.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_route_table.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_route_table.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_route_table.this.time_created
}

output "this" {
  value = oci_core_route_table.this
}
```

[top](#index)