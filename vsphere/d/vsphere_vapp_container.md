# vsphere_vapp_container

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

```terraform
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

```terraform
data "vsphere_vapp_container" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_vapp_container.this.id
}

output "this" {
  value = vsphere_vapp_container.this
}
```

[top](#index)