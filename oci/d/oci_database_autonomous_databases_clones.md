# oci_database_autonomous_databases_clones

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
module "oci_database_autonomous_databases_clones" {
  source = "./modules/oci/d/oci_database_autonomous_databases_clones"

  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = null
  # clone_type - (optional) is a type of string
  clone_type = null
  # compartment_id - (required) is a type of string
  compartment_id = null
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
variable "autonomous_database_id" {
  description = "(required)"
  type        = string
}

variable "clone_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
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
data "oci_database_autonomous_databases_clones" "this" {
  autonomous_database_id = var.autonomous_database_id
  clone_type             = var.clone_type
  compartment_id         = var.compartment_id
  display_name           = var.display_name
  state                  = var.state

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
output "autonomous_databases" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_databases_clones.this.autonomous_databases
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_databases_clones.this.id
}

output "this" {
  value = oci_database_autonomous_databases_clones.this
}
```

[top](#index)