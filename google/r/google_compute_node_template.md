# google_compute_node_template

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_node_template" {
  source = "./modules/google/r/google_compute_node_template"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # node_affinity_labels - (optional) is a type of map of string
  node_affinity_labels = {}
  # node_type - (optional) is a type of string
  node_type = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  node_type_flexibility = [{
    cpus      = null
    local_ssd = null
    memory    = null
  }]

  timeouts = [{
    create = null
    delete = null
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

variable "name" {
  description = "(optional) - Name of the resource."
  type        = string
  default     = null
}

variable "node_affinity_labels" {
  description = "(optional) - Labels to use for node affinity, which will be used in\ninstance scheduling."
  type        = map(string)
  default     = null
}

variable "node_type" {
  description = "(optional) - Node type to use for nodes group that are created from this template.\nOnly one of nodeTypeFlexibility and nodeType can be specified."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where nodes using the node template will be created.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "node_type_flexibility" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cpus      = string
      local_ssd = string
      memory    = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
resource "google_compute_node_template" "this" {
  description          = var.description
  name                 = var.name
  node_affinity_labels = var.node_affinity_labels
  node_type            = var.node_type
  project              = var.project
  region               = var.region

  dynamic "node_type_flexibility" {
    for_each = var.node_type_flexibility
    content {
      cpus   = node_type_flexibility.value["cpus"]
      memory = node_type_flexibility.value["memory"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_node_template.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_node_template.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_node_template.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_node_template.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_node_template.this.self_link
}

output "this" {
  value = google_compute_node_template.this
}
```

[top](#index)