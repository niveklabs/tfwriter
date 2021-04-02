# oci_database_vm_cluster_patch

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
module "oci_database_vm_cluster_patch" {
  source = "./modules/oci/d/oci_database_vm_cluster_patch"

  # patch_id - (required) is a type of string
  patch_id = null
  # vm_cluster_id - (required) is a type of string
  vm_cluster_id = null
}
```

[top](#index)

### Variables

```terraform
variable "patch_id" {
  description = "(required)"
  type        = string
}

variable "vm_cluster_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_vm_cluster_patch" "this" {
  patch_id      = var.patch_id
  vm_cluster_id = var.vm_cluster_id
}
```

[top](#index)

### Outputs

```terraform
output "available_actions" {
  description = "returns a list of string"
  value       = data.oci_database_vm_cluster_patch.this.available_actions
}

output "description" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch.this.description
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch.this.id
}

output "last_action" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch.this.last_action
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch.this.state
}

output "time_released" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch.this.time_released
}

output "version" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch.this.version
}

output "this" {
  value = oci_database_vm_cluster_patch.this
}
```

[top](#index)