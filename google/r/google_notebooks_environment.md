# google_notebooks_environment

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
module "google_notebooks_environment" {
  source = "./modules/google/r/google_notebooks_environment"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # post_startup_script - (optional) is a type of string
  post_startup_script = null
  # project - (optional) is a type of string
  project = null

  container_image = [{
    repository = null
    tag        = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  vm_image = [{
    image_family = null
    image_name   = null
    project      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A brief description of this environment."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of this environment for the UI."
  type        = string
  default     = null
}

variable "location" {
  description = "(required) - A reference to the zone where the machine resides."
  type        = string
}

variable "name" {
  description = "(required) - The name specified for the Environment instance.\nFormat: projects/{project_id}/locations/{location}/environments/{environmentId}"
  type        = string
}

variable "post_startup_script" {
  description = "(optional) - Path to a Bash script that automatically runs after a notebook instance fully boots up.\nThe path must be a URL or Cloud Storage path. Example: \"gs://path-to-file/file-name\""
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "container_image" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      repository = string
      tag        = string
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
      update = string
    }
  ))
  default = []
}

variable "vm_image" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      image_family = string
      image_name   = string
      project      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_notebooks_environment" "this" {
  description         = var.description
  display_name        = var.display_name
  location            = var.location
  name                = var.name
  post_startup_script = var.post_startup_script
  project             = var.project

  dynamic "container_image" {
    for_each = var.container_image
    content {
      repository = container_image.value["repository"]
      tag        = container_image.value["tag"]
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

  dynamic "vm_image" {
    for_each = var.vm_image
    content {
      image_family = vm_image.value["image_family"]
      image_name   = vm_image.value["image_name"]
      project      = vm_image.value["project"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_notebooks_environment.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_notebooks_environment.this.id
}

output "project" {
  description = "returns a string"
  value       = google_notebooks_environment.this.project
}

output "this" {
  value = google_notebooks_environment.this
}
```

[top](#index)