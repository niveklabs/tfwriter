# vra_cloud_account_vsphere

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
module "vra_cloud_account_vsphere" {
  source = "./modules/vra/r/vra_cloud_account_vsphere"

  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = null
  # associated_cloud_account_ids - (optional) is a type of list of string
  associated_cloud_account_ids = []
  # dcid - (optional) is a type of string
  dcid = null
  # description - (optional) is a type of string
  description = null
  # hostname - (required) is a type of string
  hostname = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # regions - (required) is a type of list of string
  regions = []
  # username - (required) is a type of string
  username = null

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

variable "associated_cloud_account_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dcid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "regions" {
  description = "(required)"
  type        = list(string)
}

variable "username" {
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
resource "vra_cloud_account_vsphere" "this" {
  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = var.accept_self_signed_cert
  # associated_cloud_account_ids - (optional) is a type of list of string
  associated_cloud_account_ids = var.associated_cloud_account_ids
  # dcid - (optional) is a type of string
  dcid = var.dcid
  # description - (optional) is a type of string
  description = var.description
  # hostname - (required) is a type of string
  hostname = var.hostname
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
  # regions - (required) is a type of list of string
  regions = var.regions
  # username - (required) is a type of string
  username = var.username

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
  value       = vra_cloud_account_vsphere.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = vra_cloud_account_vsphere.this.custom_properties
}

output "id" {
  description = "returns a string"
  value       = vra_cloud_account_vsphere.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_cloud_account_vsphere.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_cloud_account_vsphere.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_cloud_account_vsphere.this.owner
}

output "region_ids" {
  description = "returns a list of string"
  value       = vra_cloud_account_vsphere.this.region_ids
}

output "updated_at" {
  description = "returns a string"
  value       = vra_cloud_account_vsphere.this.updated_at
}

output "this" {
  value = vra_cloud_account_vsphere.this
}
```

[top](#index)