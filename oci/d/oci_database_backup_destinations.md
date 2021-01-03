# oci_database_backup_destinations

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
module "oci_database_backup_destinations" {
  source = "./modules/oci/d/oci_database_backup_destinations"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # type - (optional) is a type of string
  type = null

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

variable "type" {
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
data "oci_database_backup_destinations" "this" {
  compartment_id = var.compartment_id
  type           = var.type

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
output "backup_destinations" {
  description = "returns a list of object"
  value       = data.oci_database_backup_destinations.this.backup_destinations
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_backup_destinations.this.id
}

output "this" {
  value = oci_database_backup_destinations.this
}
```

[top](#index)