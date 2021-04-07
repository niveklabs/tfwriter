# brightbox_orbit_container

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_orbit_container" {
  source = "./modules/brightbox/r/brightbox_orbit_container"

  # container_read - (optional) is a type of set of string
  container_read = []
  # container_sync_key - (optional) is a type of string
  container_sync_key = null
  # container_sync_to - (optional) is a type of string
  container_sync_to = null
  # container_write - (optional) is a type of set of string
  container_write = []
  # history_location - (optional) is a type of string
  history_location = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # versions_location - (optional) is a type of string
  versions_location = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "container_read" {
  description = "(optional) - Who can read the container"
  type        = set(string)
  default     = null
}

variable "container_sync_key" {
  description = "(optional) - Container sync key"
  type        = string
  default     = null
}

variable "container_sync_to" {
  description = "(optional) - Container to sync to"
  type        = string
  default     = null
}

variable "container_write" {
  description = "(optional) - Who can write to the container"
  type        = set(string)
  default     = null
}

variable "history_location" {
  description = "(optional) - History location"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional) - Set of key/value metadata associated with the container"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the Container"
  type        = string
}

variable "versions_location" {
  description = "(optional) - Versions Location"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_orbit_container" "this" {
  # container_read - (optional) is a type of set of string
  container_read = var.container_read
  # container_sync_key - (optional) is a type of string
  container_sync_key = var.container_sync_key
  # container_sync_to - (optional) is a type of string
  container_sync_to = var.container_sync_to
  # container_write - (optional) is a type of set of string
  container_write = var.container_write
  # history_location - (optional) is a type of string
  history_location = var.history_location
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # versions_location - (optional) is a type of string
  versions_location = var.versions_location

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bytes_used" {
  description = "returns a number"
  value       = brightbox_orbit_container.this.bytes_used
}

output "created_at" {
  description = "returns a string"
  value       = brightbox_orbit_container.this.created_at
}

output "id" {
  description = "returns a string"
  value       = brightbox_orbit_container.this.id
}

output "object_count" {
  description = "returns a number"
  value       = brightbox_orbit_container.this.object_count
}

output "storage_policy" {
  description = "returns a string"
  value       = brightbox_orbit_container.this.storage_policy
}

output "this" {
  value = brightbox_orbit_container.this
}
```

[top](#index)