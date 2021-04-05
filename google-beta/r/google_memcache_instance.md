# google_memcache_instance

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_memcache_instance" {
  source = "./modules/google-beta/r/google_memcache_instance"

  # authorized_network - (optional) is a type of string
  authorized_network = null
  # display_name - (optional) is a type of string
  display_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # memcache_version - (optional) is a type of string
  memcache_version = null
  # name - (required) is a type of string
  name = null
  # node_count - (required) is a type of number
  node_count = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # zones - (optional) is a type of set of string
  zones = []

  memcache_parameters = [{
    id     = null
    params = {}
  }]

  node_config = [{
    cpu_count      = null
    memory_size_mb = null
  }]

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
variable "authorized_network" {
  description = "(optional) - The full name of the GCE network to connect the instance to.  If not provided,\n'default' will be used."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - A user-visible name for the instance."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Resource labels to represent user-provided metadata."
  type        = map(string)
  default     = null
}

variable "memcache_version" {
  description = "(optional) - The major version of Memcached software. If not provided, latest supported version will be used.\nCurrently the latest supported major version is MEMCACHE_1_5. The minor version will be automatically\ndetermined by our system based on the latest supported minor version. Default value: \"MEMCACHE_1_5\" Possible values: [\"MEMCACHE_1_5\"]"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The resource name of the instance."
  type        = string
}

variable "node_count" {
  description = "(required) - Number of nodes in the memcache instance."
  type        = number
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region of the Memcache instance. If it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "zones" {
  description = "(optional) - Zones where memcache nodes should be provisioned.  If not\nprovided, all zones will be used."
  type        = set(string)
  default     = null
}

variable "memcache_parameters" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id     = string
      params = map(string)
    }
  ))
  default = []
}

variable "node_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cpu_count      = number
      memory_size_mb = number
    }
  ))
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
resource "google_memcache_instance" "this" {
  authorized_network = var.authorized_network
  display_name       = var.display_name
  labels             = var.labels
  memcache_version   = var.memcache_version
  name               = var.name
  node_count         = var.node_count
  project            = var.project
  region             = var.region
  zones              = var.zones

  dynamic "memcache_parameters" {
    for_each = var.memcache_parameters
    content {
      params = memcache_parameters.value["params"]
    }
  }

  dynamic "node_config" {
    for_each = var.node_config
    content {
      cpu_count      = node_config.value["cpu_count"]
      memory_size_mb = node_config.value["memory_size_mb"]
    }
  }

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
output "authorized_network" {
  description = "returns a string"
  value       = google_memcache_instance.this.authorized_network
}

output "create_time" {
  description = "returns a string"
  value       = google_memcache_instance.this.create_time
}

output "discovery_endpoint" {
  description = "returns a string"
  value       = google_memcache_instance.this.discovery_endpoint
}

output "display_name" {
  description = "returns a string"
  value       = google_memcache_instance.this.display_name
}

output "id" {
  description = "returns a string"
  value       = google_memcache_instance.this.id
}

output "memcache_full_version" {
  description = "returns a string"
  value       = google_memcache_instance.this.memcache_full_version
}

output "memcache_nodes" {
  description = "returns a list of object"
  value       = google_memcache_instance.this.memcache_nodes
}

output "project" {
  description = "returns a string"
  value       = google_memcache_instance.this.project
}

output "region" {
  description = "returns a string"
  value       = google_memcache_instance.this.region
}

output "zones" {
  description = "returns a set of string"
  value       = google_memcache_instance.this.zones
}

output "this" {
  value = google_memcache_instance.this
}
```

[top](#index)