# oci_log_analytics_log_analytics_log_groups_summary

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
module "oci_log_analytics_log_analytics_log_groups_summary" {
  source = "./modules/oci/d/oci_log_analytics_log_analytics_log_groups_summary"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # namespace - (required) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_log_analytics_log_analytics_log_groups_summary" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # namespace - (required) is a type of string
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_log_groups_summary.this.id
}

output "log_group_count" {
  description = "returns a number"
  value       = data.oci_log_analytics_log_analytics_log_groups_summary.this.log_group_count
}

output "this" {
  value = oci_log_analytics_log_analytics_log_groups_summary.this
}
```

[top](#index)