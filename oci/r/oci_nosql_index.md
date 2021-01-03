# oci_nosql_index

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
module "oci_nosql_index" {
  source = "./modules/oci/r/oci_nosql_index"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # is_if_not_exists - (optional) is a type of bool
  is_if_not_exists = null
  # name - (required) is a type of string
  name = null
  # table_name_or_id - (required) is a type of string
  table_name_or_id = null

  keys = [{
    column_name     = null
    json_field_type = null
    json_path       = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_if_not_exists" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "table_name_or_id" {
  description = "(required)"
  type        = string
}

variable "keys" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      column_name     = string
      json_field_type = string
      json_path       = string
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
resource "oci_nosql_index" "this" {
  compartment_id   = var.compartment_id
  is_if_not_exists = var.is_if_not_exists
  name             = var.name
  table_name_or_id = var.table_name_or_id

  dynamic "keys" {
    for_each = var.keys
    content {
      column_name     = keys.value["column_name"]
      json_field_type = keys.value["json_field_type"]
      json_path       = keys.value["json_path"]
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
output "compartment_id" {
  description = "returns a string"
  value       = oci_nosql_index.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_nosql_index.this.id
}

output "is_if_not_exists" {
  description = "returns a bool"
  value       = oci_nosql_index.this.is_if_not_exists
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_nosql_index.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_nosql_index.this.state
}

output "table_id" {
  description = "returns a string"
  value       = oci_nosql_index.this.table_id
}

output "table_name" {
  description = "returns a string"
  value       = oci_nosql_index.this.table_name
}

output "this" {
  value = oci_nosql_index.this
}
```

[top](#index)