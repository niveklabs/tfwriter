# oci_database_databases

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
module "oci_database_databases" {
  source = "./modules/oci/d/oci_database_databases"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # db_home_id - (optional) is a type of string
  db_home_id = null
  # db_name - (optional) is a type of string
  db_name = null
  # state - (optional) is a type of string
  state = null
  # system_id - (optional) is a type of string
  system_id = null

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

variable "db_home_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_id" {
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
data "oci_database_databases" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # db_home_id - (optional) is a type of string
  db_home_id = var.db_home_id
  # db_name - (optional) is a type of string
  db_name = var.db_name
  # state - (optional) is a type of string
  state = var.state
  # system_id - (optional) is a type of string
  system_id = var.system_id

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
output "databases" {
  description = "returns a list of object"
  value       = data.oci_database_databases.this.databases
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_databases.this.id
}

output "this" {
  value = oci_database_databases.this
}
```

[top](#index)