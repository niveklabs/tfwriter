# oci_database_external_database_connectors

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
module "oci_database_external_database_connectors" {
  source = "./modules/oci/d/oci_database_external_database_connectors"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # external_database_id - (required) is a type of string
  external_database_id = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_database_id" {
  description = "(required)"
  type        = string
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
data "oci_database_external_database_connectors" "this" {
  compartment_id       = var.compartment_id
  display_name         = var.display_name
  external_database_id = var.external_database_id
  state                = var.state

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
output "external_database_connectors" {
  description = "returns a list of object"
  value       = data.oci_database_external_database_connectors.this.external_database_connectors
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_external_database_connectors.this.id
}

output "this" {
  value = oci_database_external_database_connectors.this
}
```

[top](#index)