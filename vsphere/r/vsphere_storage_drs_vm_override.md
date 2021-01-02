# vsphere_storage_drs_vm_override

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_storage_drs_vm_override" {
  source = "./modules/vsphere/r/vsphere_storage_drs_vm_override"

  # datastore_cluster_id - (required) is a type of string
  datastore_cluster_id = null
  # sdrs_automation_level - (optional) is a type of string
  sdrs_automation_level = null
  # sdrs_enabled - (optional) is a type of string
  sdrs_enabled = null
  # sdrs_intra_vm_affinity - (optional) is a type of string
  sdrs_intra_vm_affinity = null
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null
}
```

[top](#index)

### Variables

```terraform
variable "datastore_cluster_id" {
  description = "(required) - The managed object ID of the datastore cluster."
  type        = string
}

variable "sdrs_automation_level" {
  description = "(optional) - Overrides any Storage DRS automation levels for this virtual machine."
  type        = string
  default     = null
}

variable "sdrs_enabled" {
  description = "(optional) - Overrides the default Storage DRS setting for this virtual machine."
  type        = string
  default     = null
}

variable "sdrs_intra_vm_affinity" {
  description = "(optional) - Overrides the intra-VM affinity setting for this virtual machine."
  type        = string
  default     = null
}

variable "virtual_machine_id" {
  description = "(required) - The managed object ID of the virtual machine."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_storage_drs_vm_override" "this" {
  datastore_cluster_id   = var.datastore_cluster_id
  sdrs_automation_level  = var.sdrs_automation_level
  sdrs_enabled           = var.sdrs_enabled
  sdrs_intra_vm_affinity = var.sdrs_intra_vm_affinity
  virtual_machine_id     = var.virtual_machine_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_storage_drs_vm_override.this.id
}

output "this" {
  value = vsphere_storage_drs_vm_override.this
}
```

[top](#index)