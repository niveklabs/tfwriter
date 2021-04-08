# vra_zone

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
module "vra_zone" {
  source = "./modules/vra/d/vra_zone"

  # custom_properties - (optional) is a type of map of string
  custom_properties = {}
  # name - (optional) is a type of string
  name = null
  # owner - (optional) is a type of string
  owner = null

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
variable "custom_properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner" {
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

### Datasource

```terraform
data "vra_zone" "this" {
  # custom_properties - (optional) is a type of map of string
  custom_properties = var.custom_properties
  # name - (optional) is a type of string
  name = var.name
  # owner - (optional) is a type of string
  owner = var.owner

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
output "created_at" {
  description = "returns a string"
  value       = data.vra_zone.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = data.vra_zone.this.custom_properties
}

output "description" {
  description = "returns a string"
  value       = data.vra_zone.this.description
}

output "folder" {
  description = "returns a string"
  value       = data.vra_zone.this.folder
}

output "id" {
  description = "returns a string"
  value       = data.vra_zone.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vra_zone.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_zone.this.org_id
}

output "placement_policy" {
  description = "returns a string"
  value       = data.vra_zone.this.placement_policy
}

output "region_id" {
  description = "returns a string"
  value       = data.vra_zone.this.region_id
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_zone.this.updated_at
}

output "this" {
  value = vra_zone.this
}
```

[top](#index)