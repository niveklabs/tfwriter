# vra_cloud_account_vmc

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vra_cloud_account_vmc" {
  source = "./modules/vra/r/vra_cloud_account_vmc"

  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = null
  # api_token - (required) is a type of string
  api_token = null
  # dc_id - (optional) is a type of string
  dc_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # nsx_hostname - (required) is a type of string
  nsx_hostname = null
  # regions - (required) is a type of list of string
  regions = []
  # sddc_name - (required) is a type of string
  sddc_name = null
  # vcenter_hostname - (required) is a type of string
  vcenter_hostname = null
  # vcenter_password - (required) is a type of string
  vcenter_password = null
  # vcenter_username - (required) is a type of string
  vcenter_username = null

  tags = [{
    key   = null
    value = null
  }]
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nsx_hostname" {
  description = "(required)"
  type        = string
}

variable "regions" {
  description = "(required)"
  type        = list(string)
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

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_cloud_account_vmc" "this" {
  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = var.accept_self_signed_cert
  # api_token - (required) is a type of string
  api_token = var.api_token
  # dc_id - (optional) is a type of string
  dc_id = var.dc_id
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # nsx_hostname - (required) is a type of string
  nsx_hostname = var.nsx_hostname
  # regions - (required) is a type of list of string
  regions = var.regions
  # sddc_name - (required) is a type of string
  sddc_name = var.sddc_name
  # vcenter_hostname - (required) is a type of string
  vcenter_hostname = var.vcenter_hostname
  # vcenter_password - (required) is a type of string
  vcenter_password = var.vcenter_password
  # vcenter_username - (required) is a type of string
  vcenter_username = var.vcenter_username

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = vra_cloud_account_vmc.this.created_at
}

output "id" {
  description = "returns a string"
  value       = vra_cloud_account_vmc.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_cloud_account_vmc.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_cloud_account_vmc.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_cloud_account_vmc.this.owner
}

output "region_ids" {
  description = "returns a list of string"
  value       = vra_cloud_account_vmc.this.region_ids
}

output "updated_at" {
  description = "returns a string"
  value       = vra_cloud_account_vmc.this.updated_at
}

output "this" {
  value = vra_cloud_account_vmc.this
}
```

[top](#index)