# oci_nosql_table

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
module "oci_nosql_table" {
  source = "./modules/oci/r/oci_nosql_table"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # ddl_statement - (required) is a type of string
  ddl_statement = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_auto_reclaimable - (optional) is a type of bool
  is_auto_reclaimable = null
  # name - (required) is a type of string
  name = null

  table_limits = [{
    max_read_units     = null
    max_storage_in_gbs = null
    max_write_units    = null
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

variable "ddl_statement" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_auto_reclaimable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "table_limits" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      max_read_units     = number
      max_storage_in_gbs = number
      max_write_units    = number
    }
  ))
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
resource "oci_nosql_table" "this" {
  compartment_id      = var.compartment_id
  ddl_statement       = var.ddl_statement
  defined_tags        = var.defined_tags
  freeform_tags       = var.freeform_tags
  is_auto_reclaimable = var.is_auto_reclaimable
  name                = var.name

  dynamic "table_limits" {
    for_each = var.table_limits
    content {
      max_read_units     = table_limits.value["max_read_units"]
      max_storage_in_gbs = table_limits.value["max_storage_in_gbs"]
      max_write_units    = table_limits.value["max_write_units"]
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
  value       = oci_nosql_table.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_nosql_table.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_nosql_table.this.id
}

output "is_auto_reclaimable" {
  description = "returns a bool"
  value       = oci_nosql_table.this.is_auto_reclaimable
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_nosql_table.this.lifecycle_details
}

output "schema" {
  description = "returns a list of object"
  value       = oci_nosql_table.this.schema
}

output "state" {
  description = "returns a string"
  value       = oci_nosql_table.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_nosql_table.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_nosql_table.this.time_created
}

output "time_of_expiration" {
  description = "returns a string"
  value       = oci_nosql_table.this.time_of_expiration
}

output "time_updated" {
  description = "returns a string"
  value       = oci_nosql_table.this.time_updated
}

output "this" {
  value = oci_nosql_table.this
}
```

[top](#index)