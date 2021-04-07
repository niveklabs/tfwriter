# vsphere_compute_cluster

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
module "vsphere_compute_cluster" {
  source = "./modules/vsphere/d/vsphere_compute_cluster"

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
  description = "(required) - The name or absolute path to the cluster."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_compute_cluster" "this" {
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
  value       = data.vsphere_compute_cluster.this.id
}

output "resource_pool_id" {
  description = "returns a string"
  value       = data.vsphere_compute_cluster.this.resource_pool_id
}

output "this" {
  value = vsphere_compute_cluster.this
}
```

[top](#index)