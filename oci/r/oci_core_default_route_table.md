# oci_core_default_route_table

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
module "oci_core_default_route_table" {
  source = "./modules/oci/r/oci_core_default_route_table"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # manage_default_resource_id - (required) is a type of string
  manage_default_resource_id = null

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

variable "manage_default_resource_id" {
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
resource "oci_core_default_route_table" "this" {
  defined_tags               = var.defined_tags
  display_name               = var.display_name
  freeform_tags              = var.freeform_tags
  manage_default_resource_id = var.manage_default_resource_id

  dynamic "route_rules" {
    for_each = var.route_rules
    content {
      cidr_block        = route_rules.value["cidr_block"]
      description       = route_rules.value["description"]
      destination       = route_rules.value["destination"]
      destination_type  = route_rules.value["destination_type"]
      network_entity_id = route_rules.value["network_entity_id"]
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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_default_route_table.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_default_route_table.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_default_route_table.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_default_route_table.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_default_route_table.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_default_route_table.this.time_created
}

output "this" {
  value = oci_core_default_route_table.this
}
```

[top](#index)