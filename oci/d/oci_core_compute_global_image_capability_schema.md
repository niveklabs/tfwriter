# oci_core_compute_global_image_capability_schema

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
module "oci_core_compute_global_image_capability_schema" {
  source = "./modules/oci/d/oci_core_compute_global_image_capability_schema"

  # compute_global_image_capability_schema_id - (required) is a type of string
  compute_global_image_capability_schema_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compute_global_image_capability_schema_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_compute_global_image_capability_schema" "this" {
  compute_global_image_capability_schema_id = var.compute_global_image_capability_schema_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schema.this.compartment_id
}

output "current_version_name" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schema.this.current_version_name
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_compute_global_image_capability_schema.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schema.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_compute_global_image_capability_schema.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schema.this.id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schema.this.time_created
}

output "this" {
  value = oci_core_compute_global_image_capability_schema.this
}
```

[top](#index)