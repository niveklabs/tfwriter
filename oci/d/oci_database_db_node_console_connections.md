# oci_database_db_node_console_connections

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
module "oci_database_db_node_console_connections" {
  source = "./modules/oci/d/oci_database_db_node_console_connections"

  # db_node_id - (required) is a type of string
  db_node_id = null

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
variable "db_node_id" {
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
data "oci_database_db_node_console_connections" "this" {
  # db_node_id - (required) is a type of string
  db_node_id = var.db_node_id

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
output "console_connections" {
  description = "returns a list of object"
  value       = data.oci_database_db_node_console_connections.this.console_connections
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_db_node_console_connections.this.id
}

output "this" {
  value = oci_database_db_node_console_connections.this
}
```

[top](#index)