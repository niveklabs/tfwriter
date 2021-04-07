# oci_database_autonomous_databases

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
module "oci_database_autonomous_databases" {
  source = "./modules/oci/d/oci_database_autonomous_databases"

  # autonomous_container_database_id - (optional) is a type of string
  autonomous_container_database_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # db_version - (optional) is a type of string
  db_version = null
  # db_workload - (optional) is a type of string
  db_workload = null
  # display_name - (optional) is a type of string
  display_name = null
  # infrastructure_type - (optional) is a type of string
  infrastructure_type = null
  # is_data_guard_enabled - (optional) is a type of bool
  is_data_guard_enabled = null
  # is_free_tier - (optional) is a type of bool
  is_free_tier = null
  # is_refreshable_clone - (optional) is a type of bool
  is_refreshable_clone = null
  # state - (optional) is a type of string
  state = null

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
variable "autonomous_container_database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "db_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_workload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "infrastructure_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_data_guard_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_free_tier" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_refreshable_clone" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "state" {
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
data "oci_database_autonomous_databases" "this" {
  # autonomous_container_database_id - (optional) is a type of string
  autonomous_container_database_id = var.autonomous_container_database_id
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # db_version - (optional) is a type of string
  db_version = var.db_version
  # db_workload - (optional) is a type of string
  db_workload = var.db_workload
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # infrastructure_type - (optional) is a type of string
  infrastructure_type = var.infrastructure_type
  # is_data_guard_enabled - (optional) is a type of bool
  is_data_guard_enabled = var.is_data_guard_enabled
  # is_free_tier - (optional) is a type of bool
  is_free_tier = var.is_free_tier
  # is_refreshable_clone - (optional) is a type of bool
  is_refreshable_clone = var.is_refreshable_clone
  # state - (optional) is a type of string
  state = var.state

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
output "autonomous_databases" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_databases.this.autonomous_databases
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_databases.this.id
}

output "this" {
  value = oci_database_autonomous_databases.this
}
```

[top](#index)