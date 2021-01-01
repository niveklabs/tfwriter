# vsphere_compute_cluster_vm_group

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "vsphere_compute_cluster_vm_group" {
  source = "./modules/vsphere/r/vsphere_compute_cluster_vm_group"

  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
  # name - (required) is a type of string
  name = null
  # virtual_machine_ids - (optional) is a type of set of string
  virtual_machine_ids = []
}
```

[top](#index)

### Variables

```hcl
variable "compute_cluster_id" {
  description = "(required) - The managed object ID of the cluster."
  type        = string
}

variable "name" {
  description = "(required) - The unique name of the virtual machine group in the cluster."
  type        = string
}

variable "virtual_machine_ids" {
  description = "(optional) - The UUIDs of the virtual machines in this group."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_compute_cluster_vm_group" "this" {
  compute_cluster_id  = var.compute_cluster_id
  name                = var.name
  virtual_machine_ids = var.virtual_machine_ids
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = vsphere_compute_cluster_vm_group.this.id
}

output "this" {
  value = vsphere_compute_cluster_vm_group.this
}
```

[top](#index)