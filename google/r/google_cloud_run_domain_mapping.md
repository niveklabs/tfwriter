# google_cloud_run_domain_mapping

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_cloud_run_domain_mapping" {
  source = "./modules/google/r/google_cloud_run_domain_mapping"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  metadata = [{
    annotations      = {}
    generation       = null
    labels           = {}
    namespace        = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  spec = [{
    certificate_mode = null
    force_override   = null
    route_name       = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "location" {
  description = "(required) - The location of the cloud run instance. eg us-central1"
  type        = string
}

variable "name" {
  description = "(required) - Name should be a verified domain"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generation       = number
      labels           = map(string)
      namespace        = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "spec" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      certificate_mode = string
      force_override   = bool
      route_name       = string
    }
  ))
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

```hcl
resource "google_cloud_run_domain_mapping" "this" {
  location = var.location
  name     = var.name
  project  = var.project

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      namespace   = metadata.value["namespace"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      certificate_mode = spec.value["certificate_mode"]
      force_override   = spec.value["force_override"]
      route_name       = spec.value["route_name"]
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

```hcl
output "id" {
  description = "returns a string"
  value       = google_cloud_run_domain_mapping.this.id
}

output "project" {
  description = "returns a string"
  value       = google_cloud_run_domain_mapping.this.project
}

output "status" {
  description = "returns a list of object"
  value       = google_cloud_run_domain_mapping.this.status
}

output "this" {
  value = google_cloud_run_domain_mapping.this
}
```

[top](#index)