# oci_database_data_guard_associations

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
module "oci_database_data_guard_associations" {
  source = "./modules/oci/d/oci_database_data_guard_associations"

  # database_id - (required) is a type of string
  database_id = null

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
variable "database_id" {
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
data "oci_database_data_guard_associations" "this" {
  # database_id - (required) is a type of string
  database_id = var.database_id

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
output "data_guard_associations" {
  description = "returns a list of object"
  value       = data.oci_database_data_guard_associations.this.data_guard_associations
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_data_guard_associations.this.id
}

output "this" {
  value = oci_database_data_guard_associations.this
}
```

[top](#index)