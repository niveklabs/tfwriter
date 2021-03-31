# oci_core_cross_connects

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_cross_connects" {
  source = "./modules/oci/d/oci_core_cross_connects"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # cross_connect_group_id - (optional) is a type of string
  cross_connect_group_id = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "cross_connect_group_id" {
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
data "oci_core_cross_connects" "this" {
  compartment_id         = var.compartment_id
  cross_connect_group_id = var.cross_connect_group_id
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
output "cross_connects" {
  description = "returns a list of object"
  value       = data.oci_core_cross_connects.this.cross_connects
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_cross_connects.this.id
}

output "this" {
  value = oci_core_cross_connects.this
}
```

[top](#index)