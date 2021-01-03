# oci_database_db_nodes

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
module "oci_database_db_nodes" {
  source = "./modules/oci/d/oci_database_db_nodes"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # db_system_id - (optional) is a type of string
  db_system_id = null
  # state - (optional) is a type of string
  state = null
  # vm_cluster_id - (optional) is a type of string
  vm_cluster_id = null

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

variable "db_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vm_cluster_id" {
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
data "oci_database_db_nodes" "this" {
  compartment_id = var.compartment_id
  db_system_id   = var.db_system_id
  state          = var.state
  vm_cluster_id  = var.vm_cluster_id

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
output "db_nodes" {
  description = "returns a list of object"
  value       = data.oci_database_db_nodes.this.db_nodes
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_db_nodes.this.id
}

output "this" {
  value = oci_database_db_nodes.this
}
```

[top](#index)