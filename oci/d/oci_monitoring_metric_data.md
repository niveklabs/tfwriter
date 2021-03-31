# oci_monitoring_metric_data

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
module "oci_monitoring_metric_data" {
  source = "./modules/oci/d/oci_monitoring_metric_data"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
  # end_time - (optional) is a type of string
  end_time = null
  # namespace - (required) is a type of string
  namespace = null
  # query - (required) is a type of string
  query = null
  # resolution - (optional) is a type of string
  resolution = null
  # resource_group - (optional) is a type of string
  resource_group = null
  # start_time - (optional) is a type of string
  start_time = null

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

variable "end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "query" {
  description = "(required)"
  type        = string
}

variable "resolution" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_time" {
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
data "oci_monitoring_metric_data" "this" {
  compartment_id            = var.compartment_id
  compartment_id_in_subtree = var.compartment_id_in_subtree
  end_time                  = var.end_time
  namespace                 = var.namespace
  query                     = var.query
  resolution                = var.resolution
  resource_group            = var.resource_group
  start_time                = var.start_time

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
  value       = data.oci_monitoring_metric_data.this.id
}

output "metric_data" {
  description = "returns a list of object"
  value       = data.oci_monitoring_metric_data.this.metric_data
}

output "this" {
  value = oci_monitoring_metric_data.this
}
```

[top](#index)