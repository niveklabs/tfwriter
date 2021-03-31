# google_container_node_pool

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_container_node_pool" {
  source = "./modules/google/r/google_container_node_pool"

  # cluster - (required) is a type of string
  cluster = null
  # initial_node_count - (optional) is a type of number
  initial_node_count = null
  # location - (optional) is a type of string
  location = null
  # max_pods_per_node - (optional) is a type of number
  max_pods_per_node = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # node_count - (optional) is a type of number
  node_count = null
  # node_locations - (optional) is a type of set of string
  node_locations = []
  # project - (optional) is a type of string
  project = null
  # version - (optional) is a type of string
  version = null

  autoscaling = [{
    max_node_count = null
    min_node_count = null
  }]

  management = [{
    auto_repair  = null
    auto_upgrade = null
  }]

  node_config = [{
    disk_size_gb = null
    disk_type    = null
    guest_accelerator = [{
      count = null
      type  = null
    }]
    image_type       = null
    labels           = {}
    local_ssd_count  = null
    machine_type     = null
    metadata         = {}
    min_cpu_platform = null
    oauth_scopes     = []
    preemptible      = null
    service_account  = null
    shielded_instance_config = [{
      enable_integrity_monitoring = null
      enable_secure_boot          = null
    }]
    tags = []
    taint = [{
      effect = null
      key    = null
      value  = null
    }]
    workload_metadata_config = [{
      node_metadata = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  upgrade_settings = [{
    max_surge       = null
    max_unavailable = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster" {
  description = "(required) - The cluster to create the node pool for. Cluster must be present in location provided for zonal clusters."
  type        = string
}

variable "initial_node_count" {
  description = "(optional) - The initial number of nodes for the pool. In regional or multi-zonal clusters, this is the number of nodes per zone. Changing this will force recreation of the resource."
  type        = number
  default     = null
}

variable "location" {
  description = "(optional) - The location (region or zone) of the cluster."
  type        = string
  default     = null
}

variable "max_pods_per_node" {
  description = "(optional) - The maximum number of pods per node in this node pool. Note that this does not work on node pools which are \"route-based\" - that is, node pools belonging to clusters that do not have IP Aliasing enabled."
  type        = number
  default     = null
}

variable "name" {
  description = "(optional) - The name of the node pool. If left blank, Terraform will auto-generate a unique name."
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional) - Creates a unique name for the node pool beginning with the specified prefix. Conflicts with name."
  type        = string
  default     = null
}

variable "node_count" {
  description = "(optional) - The number of nodes per instance group. This field can be used to update the number of nodes per instance group but should not be used alongside autoscaling."
  type        = number
  default     = null
}

variable "node_locations" {
  description = "(optional) - The list of zones in which the node pool's nodes should be located. Nodes must be in the region of their regional cluster or in the same region as their cluster's zone for zonal clusters. If unspecified, the cluster-level node_locations will be used."
  type        = set(string)
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which to create the node pool. If blank, the provider-configured project will be used."
  type        = string
  default     = null
}

variable "version" {
  description = "(optional) - The Kubernetes version for the nodes in this pool. Note that if this field and auto_upgrade are both specified, they will fight each other for what the node version should be, so setting both is highly discouraged. While a fuzzy version can be specified, it's recommended that you specify explicit versions as Terraform will see spurious diffs when fuzzy versions are used. See the google_container_engine_versions data source's version_prefix field to approximate fuzzy versions in a Terraform-compatible way."
  type        = string
  default     = null
}

variable "autoscaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_node_count = number
      min_node_count = number
    }
  ))
  default = []
}

variable "management" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_repair  = bool
      auto_upgrade = bool
    }
  ))
  default = []
}

variable "node_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disk_size_gb = number
      disk_type    = string
      guest_accelerator = list(object(
        {
          count = number
          type  = string
        }
      ))
      image_type       = string
      labels           = map(string)
      local_ssd_count  = number
      machine_type     = string
      metadata         = map(string)
      min_cpu_platform = string
      oauth_scopes     = set(string)
      preemptible      = bool
      service_account  = string
      shielded_instance_config = list(object(
        {
          enable_integrity_monitoring = bool
          enable_secure_boot          = bool
        }
      ))
      tags = list(string)
      taint = list(object(
        {
          effect = string
          key    = string
          value  = string
        }
      ))
      workload_metadata_config = list(object(
        {
          node_metadata = string
        }
      ))
    }
  ))
  default = []
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

variable "upgrade_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_surge       = number
      max_unavailable = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_container_node_pool" "this" {
  cluster            = var.cluster
  initial_node_count = var.initial_node_count
  location           = var.location
  max_pods_per_node  = var.max_pods_per_node
  name               = var.name
  name_prefix        = var.name_prefix
  node_count         = var.node_count
  node_locations     = var.node_locations
  project            = var.project
  version            = var.version

  dynamic "autoscaling" {
    for_each = var.autoscaling
    content {
      max_node_count = autoscaling.value["max_node_count"]
      min_node_count = autoscaling.value["min_node_count"]
    }
  }

  dynamic "management" {
    for_each = var.management
    content {
      auto_repair  = management.value["auto_repair"]
      auto_upgrade = management.value["auto_upgrade"]
    }
  }

  dynamic "node_config" {
    for_each = var.node_config
    content {
      disk_size_gb      = node_config.value["disk_size_gb"]
      disk_type         = node_config.value["disk_type"]
      guest_accelerator = node_config.value["guest_accelerator"]
      image_type        = node_config.value["image_type"]
      labels            = node_config.value["labels"]
      local_ssd_count   = node_config.value["local_ssd_count"]
      machine_type      = node_config.value["machine_type"]
      metadata          = node_config.value["metadata"]
      min_cpu_platform  = node_config.value["min_cpu_platform"]
      oauth_scopes      = node_config.value["oauth_scopes"]
      preemptible       = node_config.value["preemptible"]
      service_account   = node_config.value["service_account"]
      tags              = node_config.value["tags"]
      taint             = node_config.value["taint"]

      dynamic "shielded_instance_config" {
        for_each = node_config.value.shielded_instance_config
        content {
          enable_integrity_monitoring = shielded_instance_config.value["enable_integrity_monitoring"]
          enable_secure_boot          = shielded_instance_config.value["enable_secure_boot"]
        }
      }

      dynamic "workload_metadata_config" {
        for_each = node_config.value.workload_metadata_config
        content {
          node_metadata = workload_metadata_config.value["node_metadata"]
        }
      }

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

  dynamic "upgrade_settings" {
    for_each = var.upgrade_settings
    content {
      max_surge       = upgrade_settings.value["max_surge"]
      max_unavailable = upgrade_settings.value["max_unavailable"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_container_node_pool.this.id
}

output "initial_node_count" {
  description = "returns a number"
  value       = google_container_node_pool.this.initial_node_count
}

output "instance_group_urls" {
  description = "returns a list of string"
  value       = google_container_node_pool.this.instance_group_urls
}

output "location" {
  description = "returns a string"
  value       = google_container_node_pool.this.location
}

output "max_pods_per_node" {
  description = "returns a number"
  value       = google_container_node_pool.this.max_pods_per_node
}

output "name" {
  description = "returns a string"
  value       = google_container_node_pool.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = google_container_node_pool.this.name_prefix
}

output "node_count" {
  description = "returns a number"
  value       = google_container_node_pool.this.node_count
}

output "node_locations" {
  description = "returns a set of string"
  value       = google_container_node_pool.this.node_locations
}

output "operation" {
  description = "returns a string"
  value       = google_container_node_pool.this.operation
}

output "project" {
  description = "returns a string"
  value       = google_container_node_pool.this.project
}

output "version" {
  description = "returns a string"
  value       = google_container_node_pool.this.version
}

output "this" {
  value = google_container_node_pool.this
}
```

[top](#index)