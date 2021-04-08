# vra_cloud_account_nsxt

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
module "vra_cloud_account_nsxt" {
  source = "./modules/vra/r/vra_cloud_account_nsxt"

  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = null
  # dc_id - (optional) is a type of string
  dc_id = null
  # description - (optional) is a type of string
  description = null
  # hostname - (required) is a type of string
  hostname = null
  # manager_mode - (optional) is a type of bool
  manager_mode = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
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
  description = "(optional) - Accept self signed certificate when connecting."
  type        = bool
  default     = null
}

variable "dc_id" {
  description = "(optional) - Identifier of a data collector vm deployed in the on premise infrastructure. Refer to the data-collector API to create or list data collectors."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - A human-friendly description."
  type        = string
  default     = null
}

variable "hostname" {
  description = "(required) - Host name for the NSX-T endpoint."
  type        = string
}

variable "manager_mode" {
  description = "(optional) - Create NSX-T cloud account in Manager (legacy) mode. When set to true, NSX-T cloud account is created in Manager mode. Mode cannot be changed after cloud account is created. Default value is false."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - A human-friendly name used as an identifier in APIs that support this option."
  type        = string
}

variable "password" {
  description = "(required) - Password for the user used to authenticate with the cloud Account."
  type        = string
}

variable "username" {
  description = "(required) - Username to authenticate with the cloud account."
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
resource "vra_cloud_account_nsxt" "this" {
  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = var.accept_self_signed_cert
  # dc_id - (optional) is a type of string
  dc_id = var.dc_id
  # description - (optional) is a type of string
  description = var.description
  # hostname - (required) is a type of string
  hostname = var.hostname
  # manager_mode - (optional) is a type of bool
  manager_mode = var.manager_mode
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
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
output "associated_cloud_account_ids" {
  description = "returns a list of string"
  value       = vra_cloud_account_nsxt.this.associated_cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = vra_cloud_account_nsxt.this.created_at
}

output "id" {
  description = "returns a string"
  value       = vra_cloud_account_nsxt.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_cloud_account_nsxt.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_cloud_account_nsxt.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_cloud_account_nsxt.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_cloud_account_nsxt.this.updated_at
}

output "this" {
  value = vra_cloud_account_nsxt.this
}
```

[top](#index)