# oci_monitoring_alarm_statuses

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
module "oci_monitoring_alarm_statuses" {
  source = "./modules/oci/d/oci_monitoring_alarm_statuses"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
  # display_name - (optional) is a type of string
  display_name = null

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
data "oci_monitoring_alarm_statuses" "this" {
  compartment_id            = var.compartment_id
  compartment_id_in_subtree = var.compartment_id_in_subtree
  display_name              = var.display_name

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
output "alarm_statuses" {
  description = "returns a list of object"
  value       = data.oci_monitoring_alarm_statuses.this.alarm_statuses
}

output "id" {
  description = "returns a string"
  value       = data.oci_monitoring_alarm_statuses.this.id
}

output "this" {
  value = oci_monitoring_alarm_statuses.this
}
```

[top](#index)