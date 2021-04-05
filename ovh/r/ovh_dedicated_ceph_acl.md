# ovh_dedicated_ceph_acl

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "ovh_dedicated_ceph_acl" {
  source = "./modules/ovh/r/ovh_dedicated_ceph_acl"

  # netmask - (required) is a type of string
  netmask = null
  # network - (required) is a type of string
  network = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "netmask" {
  description = "(required)"
  type        = string
}

variable "network" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_dedicated_ceph_acl" "this" {
  netmask      = var.netmask
  network      = var.network
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "family" {
  description = "returns a string"
  value       = ovh_dedicated_ceph_acl.this.family
}

output "id" {
  description = "returns a string"
  value       = ovh_dedicated_ceph_acl.this.id
}

output "this" {
  value = ovh_dedicated_ceph_acl.this
}
```

[top](#index)