# oci_nosql_indexes

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
module "oci_nosql_indexes" {
  source = "./modules/oci/d/oci_nosql_indexes"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # name - (optional) is a type of string
  name = null
  # state - (optional) is a type of string
  state = null
  # table_name_or_id - (required) is a type of string
  table_name_or_id = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_name_or_id" {
  description = "(required)"
  type        = string
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
data "oci_nosql_indexes" "this" {
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # name - (optional) is a type of string
  name = var.name
  # state - (optional) is a type of string
  state = var.state
  # table_name_or_id - (required) is a type of string
  table_name_or_id = var.table_name_or_id

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
output "id" {
  description = "returns a string"
  value       = data.oci_nosql_indexes.this.id
}

output "index_collection" {
  description = "returns a list of object"
  value       = data.oci_nosql_indexes.this.index_collection
}

output "this" {
  value = oci_nosql_indexes.this
}
```

[top](#index)