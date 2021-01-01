# vsphere_host

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
module "vsphere_host" {
  source = "./modules/vsphere/d/vsphere_host"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "datacenter_id" {
  description = "(required) - The managed object ID of the datacenter to look for the host in."
  type        = string
}

variable "name" {
  description = "(optional) - The name of the host. This can be a name or path.\tIf not provided, the default host is used."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_host" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.vsphere_host.this.id
}

output "resource_pool_id" {
  description = "returns a string"
  value       = data.vsphere_host.this.resource_pool_id
}

output "this" {
  value = vsphere_host.this
}
```

[top](#index)