# oci_waas_custom_protection_rules

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
module "oci_waas_custom_protection_rules" {
  source = "./modules/oci/d/oci_waas_custom_protection_rules"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_names - (optional) is a type of list of string
  display_names = []
  # ids - (optional) is a type of list of string
  ids = []
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

variable "display_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ids" {
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
data "oci_waas_custom_protection_rules" "this" {
  compartment_id                        = var.compartment_id
  display_names                         = var.display_names
  ids                                   = var.ids
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
output "custom_protection_rules" {
  description = "returns a list of object"
  value       = data.oci_waas_custom_protection_rules.this.custom_protection_rules
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rules.this.id
}

output "this" {
  value = oci_waas_custom_protection_rules.this
}
```

[top](#index)