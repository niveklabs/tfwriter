# oci_database_db_node_console_connection

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_db_node_console_connection" {
  source = "./modules/oci/r/oci_database_db_node_console_connection"

  # db_node_id - (required) is a type of string
  db_node_id = null
  # public_key - (required) is a type of string
  public_key = null

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "public_key" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_db_node_console_connection" "this" {
  db_node_id = var.db_node_id
  public_key = var.public_key

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = oci_database_db_node_console_connection.this.compartment_id
}

output "connection_string" {
  description = "returns a string"
  value       = oci_database_db_node_console_connection.this.connection_string
}

output "fingerprint" {
  description = "returns a string"
  value       = oci_database_db_node_console_connection.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = oci_database_db_node_console_connection.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_database_db_node_console_connection.this.state
}

output "this" {
  value = oci_database_db_node_console_connection.this
}
```

[top](#index)