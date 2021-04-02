# oci_database_db_homes

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_db_homes" {
  source = "./modules/oci/d/oci_database_db_homes"

  # backup_id - (optional) is a type of string
  backup_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # db_system_id - (optional) is a type of string
  db_system_id = null
  # db_version - (optional) is a type of string
  db_version = null
  # display_name - (optional) is a type of string
  display_name = null
  # state - (optional) is a type of string
  state = null
  # vm_cluster_id - (optional) is a type of string
  vm_cluster_id = null

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
variable "backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "db_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vm_cluster_id" {
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
data "oci_database_db_homes" "this" {
  backup_id      = var.backup_id
  compartment_id = var.compartment_id
  db_system_id   = var.db_system_id
  db_version     = var.db_version
  display_name   = var.display_name
  state          = var.state
  vm_cluster_id  = var.vm_cluster_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "db_homes" {
  description = "returns a list of object"
  value       = data.oci_database_db_homes.this.db_homes
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_db_homes.this.id
}

output "this" {
  value = oci_database_db_homes.this
}
```

[top](#index)