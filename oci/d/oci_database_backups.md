# oci_database_backups

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
module "oci_database_backups" {
  source = "./modules/oci/d/oci_database_backups"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # database_id - (optional) is a type of string
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
variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_id" {
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
data "oci_database_backups" "this" {
  compartment_id = var.compartment_id
  database_id    = var.database_id

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
output "backups" {
  description = "returns a list of object"
  value       = data.oci_database_backups.this.backups
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_backups.this.id
}

output "this" {
  value = oci_database_backups.this
}
```

[top](#index)