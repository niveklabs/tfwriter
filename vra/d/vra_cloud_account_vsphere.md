# vra_cloud_account_vsphere

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
module "vra_cloud_account_vsphere" {
  source = "./modules/vra/d/vra_cloud_account_vsphere"

  # hostname - (optional) is a type of string
  hostname = null
  # name - (optional) is a type of string
  name = null
  # username - (optional) is a type of string
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
variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
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

### Datasource

```terraform
data "vra_cloud_account_vsphere" "this" {
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # name - (optional) is a type of string
  name = var.name
  # username - (optional) is a type of string
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
  value       = data.vra_cloud_account_vsphere.this.associated_cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = data.vra_cloud_account_vsphere.this.custom_properties
}

output "dcid" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.dcid
}

output "description" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.description
}

output "enabled_region_ids" {
  description = "returns a list of string"
  value       = data.vra_cloud_account_vsphere.this.enabled_region_ids
}

output "hostname" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.updated_at
}

output "username" {
  description = "returns a string"
  value       = data.vra_cloud_account_vsphere.this.username
}

output "this" {
  value = vra_cloud_account_vsphere.this
}
```

[top](#index)