# vsphere_network

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vsphere_network" {
  source = "./modules/vsphere/d/vsphere_network"

  # datacenter_id - (optional) is a type of string
  datacenter_id = null
  # distributed_virtual_switch_uuid - (optional) is a type of string
  distributed_virtual_switch_uuid = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "datacenter_id" {
  description = "(optional) - The managed object ID of the datacenter the network is in. This is required if the supplied path is not an absolute path containing a datacenter and there are multiple datacenters in your infrastructure."
  type        = string
  default     = null
}

variable "distributed_virtual_switch_uuid" {
  description = "(optional) - Id of the distributed virtual switch of which the port group is a part of"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name or path of the network."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_network" "this" {
  datacenter_id                   = var.datacenter_id
  distributed_virtual_switch_uuid = var.distributed_virtual_switch_uuid
  name                            = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.vsphere_network.this.id
}

output "type" {
  description = "returns a string"
  value       = data.vsphere_network.this.type
}

output "this" {
  value = vsphere_network.this
}
```

[top](#index)