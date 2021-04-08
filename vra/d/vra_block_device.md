# vra_block_device

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
module "vra_block_device" {
  source = "./modules/vra/d/vra_block_device"

  # description - (optional) is a type of string
  description = null
  # expand_snapshots - (optional) is a type of bool
  expand_snapshots = null
  # filter - (optional) is a type of string
  filter = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A human-friendly description."
  type        = string
  default     = null
}

variable "expand_snapshots" {
  description = "(optional) - Indicates whether the snapshots of the block-devices should be included in the state. Applicable only for first class block devices."
  type        = bool
  default     = null
}

variable "filter" {
  description = "(optional) - Search criteria to filter the list of block devices."
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
data "vra_block_device" "this" {
  # description - (optional) is a type of string
  description = var.description
  # expand_snapshots - (optional) is a type of bool
  expand_snapshots = var.expand_snapshots
  # filter - (optional) is a type of string
  filter = var.filter

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
output "capacity_in_gb" {
  description = "returns a number"
  value       = data.vra_block_device.this.capacity_in_gb
}

output "cloud_account_ids" {
  description = "returns a list of string"
  value       = data.vra_block_device.this.cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_block_device.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = data.vra_block_device.this.custom_properties
}

output "deployment_id" {
  description = "returns a string"
  value       = data.vra_block_device.this.deployment_id
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_block_device.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_block_device.this.external_region_id
}

output "external_zone_id" {
  description = "returns a string"
  value       = data.vra_block_device.this.external_zone_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_block_device.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_block_device.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_block_device.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_block_device.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_block_device.this.owner
}

output "persistent" {
  description = "returns a bool"
  value       = data.vra_block_device.this.persistent
}

output "project_id" {
  description = "returns a string"
  value       = data.vra_block_device.this.project_id
}

output "snapshots" {
  description = "returns a list of object"
  value       = data.vra_block_device.this.snapshots
}

output "status" {
  description = "returns a string"
  value       = data.vra_block_device.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_block_device.this.updated_at
}

output "this" {
  value = vra_block_device.this
}
```

[top](#index)