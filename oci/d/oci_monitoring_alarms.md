# oci_monitoring_alarms

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
module "oci_monitoring_alarms" {
  source = "./modules/oci/d/oci_monitoring_alarms"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
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

variable "compartment_id_in_subtree" {
  description = "(optional)"
  type        = bool
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
data "oci_monitoring_alarms" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = var.compartment_id_in_subtree
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # state - (optional) is a type of string
  state = var.state

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
output "alarms" {
  description = "returns a list of object"
  value       = data.oci_monitoring_alarms.this.alarms
}

output "id" {
  description = "returns a string"
  value       = data.oci_monitoring_alarms.this.id
}

output "this" {
  value = oci_monitoring_alarms.this
}
```

[top](#index)