# vsphere_vapp_container

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
module "vsphere_vapp_container" {
  source = "./modules/vsphere/d/vsphere_vapp_container"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "datacenter_id" {
  description = "(required) - The Managed Object ID of the datacenter."
  type        = string
}

variable "name" {
  description = "(required) - The name of the vApp container."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_vapp_container" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.vsphere_vapp_container.this.id
}

output "this" {
  value = vsphere_vapp_container.this
}
```

[top](#index)