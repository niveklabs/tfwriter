# oci_logging_log_groups

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
module "oci_logging_log_groups" {
  source = "./modules/oci/d/oci_logging_log_groups"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # is_compartment_id_in_subtree - (optional) is a type of bool
  is_compartment_id_in_subtree = null

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

variable "is_compartment_id_in_subtree" {
  description = "(optional)"
  type        = bool
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
data "oci_logging_log_groups" "this" {
  compartment_id               = var.compartment_id
  display_name                 = var.display_name
  is_compartment_id_in_subtree = var.is_compartment_id_in_subtree

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
output "id" {
  description = "returns a string"
  value       = data.oci_logging_log_groups.this.id
}

output "log_groups" {
  description = "returns a list of object"
  value       = data.oci_logging_log_groups.this.log_groups
}

output "this" {
  value = oci_logging_log_groups.this
}
```

[top](#index)