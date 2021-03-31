# oci_database_autonomous_patch

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
module "oci_database_autonomous_patch" {
  source = "./modules/oci/d/oci_database_autonomous_patch"

  # autonomous_patch_id - (required) is a type of string
  autonomous_patch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_patch_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_autonomous_patch" "this" {
  autonomous_patch_id = var.autonomous_patch_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.description
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.lifecycle_details
}

output "patch_model" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.patch_model
}

output "quarter" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.quarter
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.state
}

output "time_released" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.time_released
}

output "type" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.type
}

output "version" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.version
}

output "year" {
  description = "returns a string"
  value       = data.oci_database_autonomous_patch.this.year
}

output "this" {
  value = oci_database_autonomous_patch.this
}
```

[top](#index)