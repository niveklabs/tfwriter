# vsphere_compute_cluster_vm_host_rule

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
module "vsphere_compute_cluster_vm_host_rule" {
  source = "./modules/vsphere/r/vsphere_compute_cluster_vm_host_rule"

  # affinity_host_group_name - (optional) is a type of string
  affinity_host_group_name = null
  # anti_affinity_host_group_name - (optional) is a type of string
  anti_affinity_host_group_name = null
  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
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
variable "affinity_host_group_name" {
  description = "(optional) - When this field is used, virtual machines defined in vm_group_name will be run on the hosts defined in this host group."
  type        = string
  default     = null
}

variable "anti_affinity_host_group_name" {
  description = "(optional) - When this field is used, virtual machines defined in vm_group_name will not be run on the hosts defined in this host group."
  type        = string
  default     = null
}

variable "compute_cluster_id" {
  description = "(required) - The managed object ID of the cluster."
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
  description = "(required) - The name of the virtual machine group to use with this rule."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_compute_cluster_vm_host_rule" "this" {
  # affinity_host_group_name - (optional) is a type of string
  affinity_host_group_name = var.affinity_host_group_name
  # anti_affinity_host_group_name - (optional) is a type of string
  anti_affinity_host_group_name = var.anti_affinity_host_group_name
  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = var.compute_cluster_id
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # mandatory - (optional) is a type of bool
  mandatory = var.mandatory
  # name - (required) is a type of string
  name = var.name
  # vm_group_name - (required) is a type of string
  vm_group_name = var.vm_group_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_compute_cluster_vm_host_rule.this.id
}

output "this" {
  value = vsphere_compute_cluster_vm_host_rule.this
}
```

[top](#index)