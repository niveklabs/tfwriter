# vra_cloud_account_nsxv

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
module "vra_cloud_account_nsxv" {
  source = "./modules/vra/r/vra_cloud_account_nsxv"

  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = null
  # dc_id - (optional) is a type of string
  dc_id = null
  # description - (optional) is a type of string
  description = null
  # hostname - (required) is a type of string
  hostname = null
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
  description = "(optional)"
  type        = bool
  default     = null
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
resource "vra_cloud_account_nsxv" "this" {
  # accept_self_signed_cert - (optional) is a type of bool
  accept_self_signed_cert = var.accept_self_signed_cert
  # dc_id - (optional) is a type of string
  dc_id = var.dc_id
  # description - (optional) is a type of string
  description = var.description
  # hostname - (required) is a type of string
  hostname = var.hostname
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
  value       = vra_cloud_account_nsxv.this.associated_cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = vra_cloud_account_nsxv.this.created_at
}

output "id" {
  description = "returns a string"
  value       = vra_cloud_account_nsxv.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_cloud_account_nsxv.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_cloud_account_nsxv.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_cloud_account_nsxv.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_cloud_account_nsxv.this.updated_at
}

output "this" {
  value = vra_cloud_account_nsxv.this
}
```

[top](#index)