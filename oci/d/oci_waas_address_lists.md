# oci_waas_address_lists

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
module "oci_waas_address_lists" {
  source = "./modules/oci/d/oci_waas_address_lists"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # names - (optional) is a type of list of string
  names = []
  # states - (optional) is a type of list of string
  states = []
  # time_created_greater_than_or_equal_to - (optional) is a type of string
  time_created_greater_than_or_equal_to = null
  # time_created_less_than - (optional) is a type of string
  time_created_less_than = null

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

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "states" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "time_created_greater_than_or_equal_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_less_than" {
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
data "oci_waas_address_lists" "this" {
  compartment_id                        = var.compartment_id
  ids                                   = var.ids
  names                                 = var.names
  states                                = var.states
  time_created_greater_than_or_equal_to = var.time_created_greater_than_or_equal_to
  time_created_less_than                = var.time_created_less_than

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
output "address_lists" {
  description = "returns a list of object"
  value       = data.oci_waas_address_lists.this.address_lists
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_address_lists.this.id
}

output "this" {
  value = oci_waas_address_lists.this
}
```

[top](#index)