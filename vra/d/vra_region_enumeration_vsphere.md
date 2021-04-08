# vra_region_enumeration_vsphere

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_region_enumeration_vsphere" {
  source = "./modules/vra/d/vra_region_enumeration_vsphere"

  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = null
  # dcid - (optional) is a type of string
  dcid = null
  # hostname - (required) is a type of string
  hostname = null
  # password - (required) is a type of string
  password = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "accept_self_signed_cert" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dcid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_region_enumeration_vsphere" "this" {
  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = var.accept_self_signed_cert
  # dcid - (optional) is a type of string
  dcid = var.dcid
  # hostname - (required) is a type of string
  hostname = var.hostname
  # password - (required) is a type of string
  password = var.password
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vra_region_enumeration_vsphere.this.id
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_region_enumeration_vsphere.this.regions
}

output "this" {
  value = vra_region_enumeration_vsphere.this
}
```

[top](#index)