# vsphere_compute_cluster_vm_dependency_rule

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
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_compute_cluster_vm_dependency_rule" {
  source = "./modules/vsphere/r/vsphere_compute_cluster_vm_dependency_rule"

  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
  # dependency_vm_group_name - (required) is a type of string
  dependency_vm_group_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # mandatory - (optional) is a type of bool
  mandatory = null
  # name - (required) is a type of string
  name = null
  # vm_group_name - (required) is a type of string
  vm_group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "compute_cluster_id" {
  description = "(required) - The managed object ID of the cluster."
  type        = string
}

variable "dependency_vm_group_name" {
  description = "(required) - The name of the VM group that this rule depends on. The VMs defined in the group specified by vm_group_name will not be started until the VMs in this group are started."
  type        = string
}

variable "enabled" {
  description = "(optional) - Enable this rule in the cluster."
  type        = bool
  default     = null
}

variable "mandatory" {
  description = "(optional) - When true, prevents any virtual machine operations that may violate this rule."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The unique name of the virtual machine group in the cluster."
  type        = string
}

variable "vm_group_name" {
  description = "(required) - The name of the VM group that is the subject of this rule. The VMs defined in this group will not be started until the VMs in the group specified by dependency_vm_group_name are started."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_compute_cluster_vm_dependency_rule" "this" {
  compute_cluster_id       = var.compute_cluster_id
  dependency_vm_group_name = var.dependency_vm_group_name
  enabled                  = var.enabled
  mandatory                = var.mandatory
  name                     = var.name
  vm_group_name            = var.vm_group_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_compute_cluster_vm_dependency_rule.this.id
}

output "this" {
  value = vsphere_compute_cluster_vm_dependency_rule.this
}
```

[top](#index)