# vsphere_resource_pool

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
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_resource_pool" {
  source = "./modules/vsphere/d/vsphere_resource_pool"

  # datacenter_id - (optional) is a type of string
  datacenter_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "datacenter_id" {
  description = "(optional) - The managed object ID of the datacenter the resource pool is in. This is not required when using ESXi directly, or if there is only one datacenter in your infrastructure."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name or path of the resource pool."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_resource_pool" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_resource_pool.this.id
}

output "this" {
  value = vsphere_resource_pool.this
}
```

[top](#index)