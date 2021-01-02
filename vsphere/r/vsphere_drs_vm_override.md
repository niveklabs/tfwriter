# vsphere_drs_vm_override

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
module "vsphere_drs_vm_override" {
  source = "./modules/vsphere/r/vsphere_drs_vm_override"

  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
  # drs_automation_level - (optional) is a type of string
  drs_automation_level = null
  # drs_enabled - (optional) is a type of bool
  drs_enabled = null
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compute_cluster_id" {
  description = "(required) - The managed object ID of the cluster."
  type        = string
}

variable "drs_automation_level" {
  description = "(optional) - The automation level for this virtual machine in the cluster. Can be one of manual, partiallyAutomated, or fullyAutomated."
  type        = string
  default     = null
}

variable "drs_enabled" {
  description = "(optional) - Enable DRS for this virtual machine."
  type        = bool
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
resource "vsphere_drs_vm_override" "this" {
  compute_cluster_id   = var.compute_cluster_id
  drs_automation_level = var.drs_automation_level
  drs_enabled          = var.drs_enabled
  virtual_machine_id   = var.virtual_machine_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_drs_vm_override.this.id
}

output "this" {
  value = vsphere_drs_vm_override.this
}
```

[top](#index)