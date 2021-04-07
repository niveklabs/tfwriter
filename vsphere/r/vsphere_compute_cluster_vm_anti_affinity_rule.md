# vsphere_compute_cluster_vm_anti_affinity_rule

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
module "vsphere_compute_cluster_vm_anti_affinity_rule" {
  source = "./modules/vsphere/r/vsphere_compute_cluster_vm_anti_affinity_rule"

  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
  # enabled - (optional) is a type of bool
  enabled = null
  # mandatory - (optional) is a type of bool
  mandatory = null
  # name - (required) is a type of string
  name = null
  # virtual_machine_ids - (required) is a type of set of string
  virtual_machine_ids = []
}
```

[top](#index)

### Variables

```terraform
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

variable "virtual_machine_ids" {
  description = "(required) - The UUIDs of the virtual machines to run on hosts different from each other."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_compute_cluster_vm_anti_affinity_rule" "this" {
  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = var.compute_cluster_id
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # mandatory - (optional) is a type of bool
  mandatory = var.mandatory
  # name - (required) is a type of string
  name = var.name
  # virtual_machine_ids - (required) is a type of set of string
  virtual_machine_ids = var.virtual_machine_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_compute_cluster_vm_anti_affinity_rule.this.id
}

output "this" {
  value = vsphere_compute_cluster_vm_anti_affinity_rule.this
}
```

[top](#index)