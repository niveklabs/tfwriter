# ovh_dedicated_ceph

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_dedicated_ceph" {
  source = "./modules/ovh/d/ovh_dedicated_ceph"

  # ceph_version - (optional) is a type of string
  ceph_version = null
  # service_name - (required) is a type of string
  service_name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "ceph_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ovh_dedicated_ceph" "this" {
  # ceph_version - (optional) is a type of string
  ceph_version = var.ceph_version
  # service_name - (required) is a type of string
  service_name = var.service_name
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "ceph_mons" {
  description = "returns a list of string"
  value       = data.ovh_dedicated_ceph.this.ceph_mons
}

output "ceph_version" {
  description = "returns a string"
  value       = data.ovh_dedicated_ceph.this.ceph_version
}

output "crush_tunables" {
  description = "returns a string"
  value       = data.ovh_dedicated_ceph.this.crush_tunables
}

output "id" {
  description = "returns a string"
  value       = data.ovh_dedicated_ceph.this.id
}

output "label" {
  description = "returns a string"
  value       = data.ovh_dedicated_ceph.this.label
}

output "region" {
  description = "returns a string"
  value       = data.ovh_dedicated_ceph.this.region
}

output "size" {
  description = "returns a number"
  value       = data.ovh_dedicated_ceph.this.size
}

output "state" {
  description = "returns a string"
  value       = data.ovh_dedicated_ceph.this.state
}

output "status" {
  description = "returns a string"
  value       = data.ovh_dedicated_ceph.this.status
}

output "this" {
  value = ovh_dedicated_ceph.this
}
```

[top](#index)