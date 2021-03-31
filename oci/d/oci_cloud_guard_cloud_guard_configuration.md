# oci_cloud_guard_cloud_guard_configuration

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
module "oci_cloud_guard_cloud_guard_configuration" {
  source = "./modules/oci/d/oci_cloud_guard_cloud_guard_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_cloud_guard_cloud_guard_configuration" "this" {
  compartment_id = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_cloud_guard_configuration.this.id
}

output "reporting_region" {
  description = "returns a string"
  value       = data.oci_cloud_guard_cloud_guard_configuration.this.reporting_region
}

output "self_manage_resources" {
  description = "returns a bool"
  value       = data.oci_cloud_guard_cloud_guard_configuration.this.self_manage_resources
}

output "status" {
  description = "returns a string"
  value       = data.oci_cloud_guard_cloud_guard_configuration.this.status
}

output "this" {
  value = oci_cloud_guard_cloud_guard_configuration.this
}
```

[top](#index)