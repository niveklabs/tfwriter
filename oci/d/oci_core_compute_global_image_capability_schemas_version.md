# oci_core_compute_global_image_capability_schemas_version

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
module "oci_core_compute_global_image_capability_schemas_version" {
  source = "./modules/oci/d/oci_core_compute_global_image_capability_schemas_version"

  # compute_global_image_capability_schema_id - (required) is a type of string
  compute_global_image_capability_schema_id = null
  # compute_global_image_capability_schema_version_name - (required) is a type of string
  compute_global_image_capability_schema_version_name = null
}
```

[top](#index)

### Variables

```terraform
variable "compute_global_image_capability_schema_id" {
  description = "(required)"
  type        = string
}

variable "compute_global_image_capability_schema_version_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_compute_global_image_capability_schemas_version" "this" {
  compute_global_image_capability_schema_id           = var.compute_global_image_capability_schema_id
  compute_global_image_capability_schema_version_name = var.compute_global_image_capability_schema_version_name
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schemas_version.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schemas_version.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schemas_version.this.name
}

output "schema_data" {
  description = "returns a map of string"
  value       = data.oci_core_compute_global_image_capability_schemas_version.this.schema_data
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schemas_version.this.time_created
}

output "this" {
  value = oci_core_compute_global_image_capability_schemas_version.this
}
```

[top](#index)