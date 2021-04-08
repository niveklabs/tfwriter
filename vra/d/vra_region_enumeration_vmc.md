# vra_region_enumeration_vmc

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
module "vra_region_enumeration_vmc" {
  source = "./modules/vra/d/vra_region_enumeration_vmc"

  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = null
  # api_token - (required) is a type of string
  api_token = null
  # dc_id - (optional) is a type of string
  dc_id = null
  # sddc_name - (required) is a type of string
  sddc_name = null
  # vcenter_hostname - (required) is a type of string
  vcenter_hostname = null
  # vcenter_password - (required) is a type of string
  vcenter_password = null
  # vcenter_username - (required) is a type of string
  vcenter_username = null
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

variable "api_token" {
  description = "(required)"
  type        = string
}

variable "dc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sddc_name" {
  description = "(required)"
  type        = string
}

variable "vcenter_hostname" {
  description = "(required)"
  type        = string
}

variable "vcenter_password" {
  description = "(required)"
  type        = string
}

variable "vcenter_username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_region_enumeration_vmc" "this" {
  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = var.accept_self_signed_cert
  # api_token - (required) is a type of string
  api_token = var.api_token
  # dc_id - (optional) is a type of string
  dc_id = var.dc_id
  # sddc_name - (required) is a type of string
  sddc_name = var.sddc_name
  # vcenter_hostname - (required) is a type of string
  vcenter_hostname = var.vcenter_hostname
  # vcenter_password - (required) is a type of string
  vcenter_password = var.vcenter_password
  # vcenter_username - (required) is a type of string
  vcenter_username = var.vcenter_username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vra_region_enumeration_vmc.this.id
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_region_enumeration_vmc.this.regions
}

output "this" {
  value = vra_region_enumeration_vmc.this
}
```

[top](#index)