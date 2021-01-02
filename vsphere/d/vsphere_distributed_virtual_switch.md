# vsphere_distributed_virtual_switch

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
module "vsphere_distributed_virtual_switch" {
  source = "./modules/vsphere/d/vsphere_distributed_virtual_switch"

  # datacenter_id - (optional) is a type of string
  datacenter_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "datacenter_id" {
  description = "(optional) - The managed object ID of the datacenter the DVS is in. This is required if the supplied path is not an absolute path containing a datacenter and there are multiple datacenters in your infrastructure."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the distributed virtual switch. This can be a name or path."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_distributed_virtual_switch" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_distributed_virtual_switch.this.id
}

output "uplinks" {
  description = "returns a list of string"
  value       = data.vsphere_distributed_virtual_switch.this.uplinks
}

output "this" {
  value = vsphere_distributed_virtual_switch.this
}
```

[top](#index)