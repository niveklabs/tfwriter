# gridscale_isoimage

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
module "gridscale_isoimage" {
  source = "./modules/gridscale/r/gridscale_isoimage"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # source_url - (required) is a type of string
  source_url = null

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

variable "source_url" {
  description = "(required) - Contains the source URL of the ISO image that it was originally fetched from."
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
resource "gridscale_isoimage" "this" {
  labels     = var.labels
  name       = var.name
  source_url = var.source_url

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
  value       = gridscale_isoimage.this.capacity
}

output "change_time" {
  description = "returns a string"
  value       = gridscale_isoimage.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_isoimage.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_isoimage.this.current_price
}

output "description" {
  description = "returns a string"
  value       = gridscale_isoimage.this.description
}

output "id" {
  description = "returns a string"
  value       = gridscale_isoimage.this.id
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_isoimage.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_isoimage.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_isoimage.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_isoimage.this.location_uuid
}

output "private" {
  description = "returns a bool"
  value       = gridscale_isoimage.this.private
}

output "server" {
  description = "returns a set of object"
  value       = gridscale_isoimage.this.server
}

output "status" {
  description = "returns a string"
  value       = gridscale_isoimage.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = gridscale_isoimage.this.usage_in_minutes
}

output "version" {
  description = "returns a string"
  value       = gridscale_isoimage.this.version
}

output "this" {
  value = gridscale_isoimage.this
}
```

[top](#index)