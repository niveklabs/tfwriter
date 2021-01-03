# oci_database_autonomous_container_database_dataguard_associations

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_container_database_dataguard_associations" {
  source = "./modules/oci/d/oci_database_autonomous_container_database_dataguard_associations"

  # autonomous_container_database_id - (required) is a type of string
  autonomous_container_database_id = null

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
data "oci_database_autonomous_container_database_dataguard_associations" "this" {
  autonomous_container_database_id = var.autonomous_container_database_id

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
output "autonomous_container_database_dataguard_associations" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_container_database_dataguard_associations.this.autonomous_container_database_dataguard_associations
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_container_database_dataguard_associations.this.id
}

output "this" {
  value = oci_database_autonomous_container_database_dataguard_associations.this
}
```

[top](#index)