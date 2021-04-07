# oci_database_vm_cluster_patch_history_entry

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
module "oci_database_vm_cluster_patch_history_entry" {
  source = "./modules/oci/d/oci_database_vm_cluster_patch_history_entry"

  # patch_history_entry_id - (required) is a type of string
  patch_history_entry_id = null
  # vm_cluster_id - (required) is a type of string
  vm_cluster_id = null
}
```

[top](#index)

### Variables

```terraform
variable "patch_history_entry_id" {
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
data "oci_database_vm_cluster_patch_history_entry" "this" {
  # patch_history_entry_id - (required) is a type of string
  patch_history_entry_id = var.patch_history_entry_id
  # vm_cluster_id - (required) is a type of string
  vm_cluster_id = var.vm_cluster_id
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch_history_entry.this.action
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch_history_entry.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch_history_entry.this.lifecycle_details
}

output "patch_id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch_history_entry.this.patch_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch_history_entry.this.state
}

output "time_ended" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch_history_entry.this.time_ended
}

output "time_started" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_patch_history_entry.this.time_started
}

output "this" {
  value = oci_database_vm_cluster_patch_history_entry.this
}
```

[top](#index)