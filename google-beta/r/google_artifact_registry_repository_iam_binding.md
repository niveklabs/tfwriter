# google_artifact_registry_repository_iam_binding

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_artifact_registry_repository_iam_binding" {
  source = "./modules/google-beta/r/google_artifact_registry_repository_iam_binding"

  # location - (optional) is a type of string
  location = null
  # members - (required) is a type of set of string
  members = []
  # project - (optional) is a type of string
  project = null
  # repository - (required) is a type of string
  repository = null
  # role - (required) is a type of string
  role = null

  condition = [{
    description = null
    expression  = null
    title       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      expression  = string
      title       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_artifact_registry_repository_iam_binding" "this" {
  location   = var.location
  members    = var.members
  project    = var.project
  repository = var.repository
  role       = var.role

  dynamic "condition" {
    for_each = var.condition
    content {
      description = condition.value["description"]
      expression  = condition.value["expression"]
      title       = condition.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_artifact_registry_repository_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_artifact_registry_repository_iam_binding.this.id
}

output "location" {
  description = "returns a string"
  value       = google_artifact_registry_repository_iam_binding.this.location
}

output "project" {
  description = "returns a string"
  value       = google_artifact_registry_repository_iam_binding.this.project
}

output "this" {
  value = google_artifact_registry_repository_iam_binding.this
}
```

[top](#index)