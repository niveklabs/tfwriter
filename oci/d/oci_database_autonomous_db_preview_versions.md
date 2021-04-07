# oci_database_autonomous_db_preview_versions

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
module "oci_database_autonomous_db_preview_versions" {
  source = "./modules/oci/d/oci_database_autonomous_db_preview_versions"

  # compartment_id - (required) is a type of string
  compartment_id = null

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
data "oci_database_autonomous_db_preview_versions" "this" {
  compartment_id = var.compartment_id

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
output "autonomous_db_preview_versions" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_db_preview_versions.this.autonomous_db_preview_versions
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_db_preview_versions.this.id
}

output "this" {
  value = oci_database_autonomous_db_preview_versions.this
}
```

[top](#index)