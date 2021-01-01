# vsphere_compute_cluster_host_group

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
module "vsphere_compute_cluster_host_group" {
  source = "./modules/vsphere/r/vsphere_compute_cluster_host_group"

  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
  # host_system_ids - (optional) is a type of set of string
  host_system_ids = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "compute_cluster_id" {
  description = "(required) - The managed object ID of the cluster."
  type        = string
}

variable "host_system_ids" {
  description = "(optional) - The managed object IDs of the hosts."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The unique name of the virtual machine group in the cluster."
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_compute_cluster_host_group" "this" {
  compute_cluster_id = var.compute_cluster_id
  host_system_ids    = var.host_system_ids
  name               = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = vsphere_compute_cluster_host_group.this.id
}

output "this" {
  value = vsphere_compute_cluster_host_group.this
}
```

[top](#index)