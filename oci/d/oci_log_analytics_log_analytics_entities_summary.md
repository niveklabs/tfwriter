# oci_log_analytics_log_analytics_entities_summary

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
module "oci_log_analytics_log_analytics_entities_summary" {
  source = "./modules/oci/d/oci_log_analytics_log_analytics_entities_summary"

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
data "oci_log_analytics_log_analytics_entities_summary" "this" {
  compartment_id = var.compartment_id
  namespace      = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "active_entities_count" {
  description = "returns a number"
  value       = data.oci_log_analytics_log_analytics_entities_summary.this.active_entities_count
}

output "entities_with_has_logs_collected_count" {
  description = "returns a number"
  value       = data.oci_log_analytics_log_analytics_entities_summary.this.entities_with_has_logs_collected_count
}

output "entities_with_management_agent_count" {
  description = "returns a number"
  value       = data.oci_log_analytics_log_analytics_entities_summary.this.entities_with_management_agent_count
}

output "id" {
  description = "returns a string"
  value       = data.oci_log_analytics_log_analytics_entities_summary.this.id
}

output "this" {
  value = oci_log_analytics_log_analytics_entities_summary.this
}
```

[top](#index)