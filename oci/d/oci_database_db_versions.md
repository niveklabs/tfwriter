# oci_database_db_versions

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "oci_database_db_versions" {
  source = "./modules/oci/d/oci_database_db_versions"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # db_system_id - (optional) is a type of string
  db_system_id = null
  # db_system_shape - (optional) is a type of string
  db_system_shape = null
  # is_upgrade_supported - (optional) is a type of bool
  is_upgrade_supported = null
  # storage_management - (optional) is a type of string
  storage_management = null

  filter = [{
    name   = null
    regex  = null
    values = []
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

variable "db_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_system_shape" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_upgrade_supported" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "storage_management" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_db_versions" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # db_system_id - (optional) is a type of string
  db_system_id = var.db_system_id
  # db_system_shape - (optional) is a type of string
  db_system_shape = var.db_system_shape
  # is_upgrade_supported - (optional) is a type of bool
  is_upgrade_supported = var.is_upgrade_supported
  # storage_management - (optional) is a type of string
  storage_management = var.storage_management

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "db_versions" {
  description = "returns a list of object"
  value       = data.oci_database_db_versions.this.db_versions
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_db_versions.this.id
}

output "this" {
  value = oci_database_db_versions.this
}
```

[top](#index)