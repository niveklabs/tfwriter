# vra_zone

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
module "vra_zone" {
  source = "./modules/vra/r/vra_zone"

  # description - (optional) is a type of string
  description = null
  # folder - (optional) is a type of string
  folder = null
  # name - (required) is a type of string
  name = null
  # placement_policy - (optional) is a type of string
  placement_policy = null
  # region_id - (required) is a type of string
  region_id = null

  tags = [{
    key   = null
    value = null
  }]

  tags_to_match = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A human-friendly description for the zone"
  type        = string
  default     = null
}

variable "folder" {
  description = "(optional) - The folder relative path to the datacenter where resources are deployed to. (only applicable for vSphere cloud zones)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - A human-friendly name for the zone"
  type        = string
}

variable "placement_policy" {
  description = "(optional) - Placement policy for the zone. One of DEFAULT, SPREAD or BINPACK."
  type        = string
  default     = null
}

variable "region_id" {
  description = "(required) - The id of the region for which this profile is created"
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

variable "tags_to_match" {
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
resource "vra_zone" "this" {
  # description - (optional) is a type of string
  description = var.description
  # folder - (optional) is a type of string
  folder = var.folder
  # name - (required) is a type of string
  name = var.name
  # placement_policy - (optional) is a type of string
  placement_policy = var.placement_policy
  # region_id - (required) is a type of string
  region_id = var.region_id

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

  dynamic "tags_to_match" {
    for_each = var.tags_to_match
    content {
      # key - (required) is a type of string
      key = tags_to_match.value["key"]
      # value - (required) is a type of string
      value = tags_to_match.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_account_id" {
  description = "returns a string"
  value       = vra_zone.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = vra_zone.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = vra_zone.this.custom_properties
}

output "external_region_id" {
  description = "returns a map of string"
  value       = vra_zone.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_zone.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_zone.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_zone.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_zone.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_zone.this.updated_at
}

output "this" {
  value = vra_zone.this
}
```

[top](#index)