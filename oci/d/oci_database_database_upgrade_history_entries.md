# oci_database_database_upgrade_history_entries

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
module "oci_database_database_upgrade_history_entries" {
  source = "./modules/oci/d/oci_database_database_upgrade_history_entries"

  # database_id - (required) is a type of string
  database_id = null
  # state - (optional) is a type of string
  state = null
  # upgrade_action - (optional) is a type of string
  upgrade_action = null

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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upgrade_action" {
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
data "oci_database_database_upgrade_history_entries" "this" {
  database_id    = var.database_id
  state          = var.state
  upgrade_action = var.upgrade_action

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
output "database_upgrade_history_entries" {
  description = "returns a list of object"
  value       = data.oci_database_database_upgrade_history_entries.this.database_upgrade_history_entries
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_database_upgrade_history_entries.this.id
}

output "this" {
  value = oci_database_database_upgrade_history_entries.this
}
```

[top](#index)