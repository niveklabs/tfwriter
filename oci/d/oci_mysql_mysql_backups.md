# oci_mysql_mysql_backups

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
module "oci_mysql_mysql_backups" {
  source = "./modules/oci/d/oci_mysql_mysql_backups"

  # backup_id - (optional) is a type of string
  backup_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # creation_type - (optional) is a type of string
  creation_type = null
  # db_system_id - (optional) is a type of string
  db_system_id = null
  # display_name - (optional) is a type of string
  display_name = null
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
variable "backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "creation_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_system_id" {
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
data "oci_mysql_mysql_backups" "this" {
  backup_id      = var.backup_id
  compartment_id = var.compartment_id
  creation_type  = var.creation_type
  db_system_id   = var.db_system_id
  display_name   = var.display_name
  state          = var.state

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
  value       = data.oci_mysql_mysql_backups.this.backups
}

output "id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_backups.this.id
}

output "this" {
  value = oci_mysql_mysql_backups.this
}
```

[top](#index)