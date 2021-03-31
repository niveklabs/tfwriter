# google_compute_node_group

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_node_group" {
  source = "./modules/google-beta/r/google_compute_node_group"

  # description - (optional) is a type of string
  description = null
  # maintenance_policy - (optional) is a type of string
  maintenance_policy = null
  # name - (optional) is a type of string
  name = null
  # node_template - (required) is a type of string
  node_template = null
  # project - (optional) is a type of string
  project = null
  # size - (required) is a type of number
  size = null
  # zone - (optional) is a type of string
  zone = null

  autoscaling_policy = [{
    max_nodes = null
    min_nodes = null
    mode      = null
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
variable "description" {
  description = "(optional) - An optional textual description of the resource."
  type        = string
  default     = null
}

variable "maintenance_policy" {
  description = "(optional) - Specifies how to handle instances when a node in the group undergoes maintenance. Set to one of: DEFAULT, RESTART_IN_PLACE, or MIGRATE_WITHIN_NODE_GROUP. The default value is DEFAULT."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the resource."
  type        = string
  default     = null
}

variable "node_template" {
  description = "(required) - The URL of the node template to which this node group belongs."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(required) - The total number of nodes in the node group."
  type        = number
}

variable "zone" {
  description = "(optional) - Zone where this node group is located"
  type        = string
  default     = null
}

variable "autoscaling_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_nodes = number
      min_nodes = number
      mode      = string
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
```

[top](#index)

### Resource

```terraform
resource "google_compute_node_group" "this" {
  description        = var.description
  maintenance_policy = var.maintenance_policy
  name               = var.name
  node_template      = var.node_template
  project            = var.project
  size               = var.size
  zone               = var.zone

  dynamic "autoscaling_policy" {
    for_each = var.autoscaling_policy
    content {
      max_nodes = autoscaling_policy.value["max_nodes"]
      min_nodes = autoscaling_policy.value["min_nodes"]
      mode      = autoscaling_policy.value["mode"]
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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_node_group.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_node_group.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_node_group.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_node_group.this.self_link
}

output "zone" {
  description = "returns a string"
  value       = google_compute_node_group.this.zone
}

output "this" {
  value = google_compute_node_group.this
}
```

[top](#index)