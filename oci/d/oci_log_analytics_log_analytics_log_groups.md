# oci_log_analytics_log_analytics_log_groups

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
module "oci_log_analytics_log_analytics_log_groups" {
  source = "./modules/oci/d/oci_log_analytics_log_analytics_log_groups"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # namespace - (required) is a type of string
  namespace = null

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

variable "namespace" {
  description = "(required)"
  type        = string
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
data "oci_log_analytics_log_analytics_log_groups" "this" {
  compartment_id = var.compartment_id
  display_name   = var.display_name
  namespace      = var.namespace

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
  value       = data.oci_log_analytics_log_analytics_log_groups.this.id
}

output "log_analytics_log_group_summary_collection" {
  description = "returns a list of object"
  value       = data.oci_log_analytics_log_analytics_log_groups.this.log_analytics_log_group_summary_collection
}

output "this" {
  value = oci_log_analytics_log_analytics_log_groups.this
}
```

[top](#index)