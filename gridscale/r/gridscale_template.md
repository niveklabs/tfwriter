# gridscale_template

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_template" {
  source = "./modules/gridscale/r/gridscale_template"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # snapshot_uuid - (required) is a type of string
  snapshot_uuid = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters."
  type        = string
}

variable "snapshot_uuid" {
  description = "(required) - Snapshot uuid for template."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "gridscale_template" "this" {
  labels        = var.labels
  name          = var.name
  snapshot_uuid = var.snapshot_uuid

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "capacity" {
  description = "returns a number"
  value       = gridscale_template.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = gridscale_template.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_template.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_template.this.current_price
}

output "description" {
  description = "returns a string"
  value       = gridscale_template.this.description
}

output "distro" {
  description = "returns a string"
  value       = gridscale_template.this.distro
}

output "id" {
  description = "returns a string"
  value       = gridscale_template.this.id
}

output "license_product_no" {
  description = "returns a number"
  value       = gridscale_template.this.license_product_no
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_template.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_template.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_template.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_template.this.location_uuid
}

output "ostype" {
  description = "returns a string"
  value       = gridscale_template.this.ostype
}

output "private" {
  description = "returns a bool"
  value       = gridscale_template.this.private
}

output "status" {
  description = "returns a string"
  value       = gridscale_template.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = gridscale_template.this.usage_in_minutes
}

output "version" {
  description = "returns a string"
  value       = gridscale_template.this.version
}

output "this" {
  value = gridscale_template.this
}
```

[top](#index)