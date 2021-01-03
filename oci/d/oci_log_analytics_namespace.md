# oci_log_analytics_namespace

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_log_analytics_namespace" {
  source = "./modules/oci/d/oci_log_analytics_namespace"

  # namespace - (required) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "namespace" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_log_analytics_namespace" "this" {
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_log_analytics_namespace.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_log_analytics_namespace.this.id
}

output "is_onboarded" {
  description = "returns a bool"
  value       = data.oci_log_analytics_namespace.this.is_onboarded
}

output "this" {
  value = oci_log_analytics_namespace.this
}
```

[top](#index)