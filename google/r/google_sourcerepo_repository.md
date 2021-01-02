# google_sourcerepo_repository

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
module "google_sourcerepo_repository" {
  source = "./modules/google/r/google_sourcerepo_repository"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  pubsub_configs = [{
    message_format        = null
    service_account_email = null
    topic                 = null
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
variable "name" {
  description = "(required) - Resource name of the repository, of the form '{{repo}}'.\nThe repo name may contain slashes. eg, 'name/with/slash'"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pubsub_configs" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      message_format        = string
      service_account_email = string
      topic                 = string
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
```

[top](#index)

### Resource

```terraform
resource "google_sourcerepo_repository" "this" {
  name    = var.name
  project = var.project

  dynamic "pubsub_configs" {
    for_each = var.pubsub_configs
    content {
      message_format        = pubsub_configs.value["message_format"]
      service_account_email = pubsub_configs.value["service_account_email"]
      topic                 = pubsub_configs.value["topic"]
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
output "id" {
  description = "returns a string"
  value       = google_sourcerepo_repository.this.id
}

output "project" {
  description = "returns a string"
  value       = google_sourcerepo_repository.this.project
}

output "size" {
  description = "returns a number"
  value       = google_sourcerepo_repository.this.size
}

output "url" {
  description = "returns a string"
  value       = google_sourcerepo_repository.this.url
}

output "this" {
  value = google_sourcerepo_repository.this
}
```

[top](#index)