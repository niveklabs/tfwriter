# oci_monitoring_metrics

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
module "oci_monitoring_metrics" {
  source = "./modules/oci/d/oci_monitoring_metrics"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
  # dimension_filters - (optional) is a type of map of string
  dimension_filters = {}
  # group_by - (optional) is a type of list of string
  group_by = []
  # name - (optional) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # resource_group - (optional) is a type of string
  resource_group = null

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

variable "dimension_filters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "group_by" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group" {
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
data "oci_monitoring_metrics" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = var.compartment_id_in_subtree
  # dimension_filters - (optional) is a type of map of string
  dimension_filters = var.dimension_filters
  # group_by - (optional) is a type of list of string
  group_by = var.group_by
  # name - (optional) is a type of string
  name = var.name
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # resource_group - (optional) is a type of string
  resource_group = var.resource_group

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
output "id" {
  description = "returns a string"
  value       = data.oci_monitoring_metrics.this.id
}

output "metrics" {
  description = "returns a list of object"
  value       = data.oci_monitoring_metrics.this.metrics
}

output "this" {
  value = oci_monitoring_metrics.this
}
```

[top](#index)