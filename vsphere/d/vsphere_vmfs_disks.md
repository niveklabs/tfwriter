# vsphere_vmfs_disks

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vsphere_vmfs_disks" {
  source = "./modules/vsphere/d/vsphere_vmfs_disks"

  # filter - (optional) is a type of string
  filter = null
  # host_system_id - (required) is a type of string
  host_system_id = null
  # rescan - (optional) is a type of bool
  rescan = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional) - A regular expression to filter the disks against. Only disks with canonical names that match will be included."
  type        = string
  default     = null
}

variable "host_system_id" {
  description = "(required) - The managed object ID of the host to search for disks on."
  type        = string
}

variable "rescan" {
  description = "(optional) - Rescan the system for disks before querying. This may lengthen the time it takes to gather information."
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_vmfs_disks" "this" {
  filter         = var.filter
  host_system_id = var.host_system_id
  rescan         = var.rescan
}
```

[top](#index)

### Outputs

```terraform
output "disks" {
  description = "returns a list of string"
  value       = data.vsphere_vmfs_disks.this.disks
}

output "id" {
  description = "returns a string"
  value       = data.vsphere_vmfs_disks.this.id
}

output "this" {
  value = vsphere_vmfs_disks.this
}
```

[top](#index)