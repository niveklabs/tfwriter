# vsphere_datastore

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
module "vsphere_datastore" {
  source = "./modules/vsphere/d/vsphere_datastore"

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
  description = "(optional) - The managed object ID of the datacenter the datastore is in. This is not required when using ESXi directly, or if there is only one datacenter in your infrastructure."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name or path of the datastore."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_datastore" "this" {
  # datacenter_id - (optional) is a type of string
  datacenter_id = var.datacenter_id
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_datastore.this.id
}

output "this" {
  value = vsphere_datastore.this
}
```

[top](#index)