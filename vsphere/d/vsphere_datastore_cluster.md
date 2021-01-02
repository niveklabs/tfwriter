# vsphere_datastore_cluster

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
module "vsphere_datastore_cluster" {
  source = "./modules/vsphere/d/vsphere_datastore_cluster"

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
  description = "(optional) - The managed object ID of the datacenter the cluster is located in. Not required if using an absolute path."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name or absolute path to the datastore cluster."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_datastore_cluster" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_datastore_cluster.this.id
}

output "this" {
  value = vsphere_datastore_cluster.this
}
```

[top](#index)