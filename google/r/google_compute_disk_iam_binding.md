# google_compute_disk_iam_binding

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_disk_iam_binding" {
  source = "./modules/google/r/google_compute_disk_iam_binding"

  # members - (required) is a type of set of string
  members = []
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # role - (required) is a type of string
  role = null
  # zone - (optional) is a type of string
  zone = null

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
variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "zone" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "google_compute_disk_iam_binding" "this" {
  # members - (required) is a type of set of string
  members = var.members
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # role - (required) is a type of string
  role = var.role
  # zone - (optional) is a type of string
  zone = var.zone

  dynamic "condition" {
    for_each = var.condition
    content {
      # description - (optional) is a type of string
      description = condition.value["description"]
      # expression - (required) is a type of string
      expression = condition.value["expression"]
      # title - (required) is a type of string
      title = condition.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_compute_disk_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_compute_disk_iam_binding.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_disk_iam_binding.this.project
}

output "zone" {
  description = "returns a string"
  value       = google_compute_disk_iam_binding.this.zone
}

output "this" {
  value = google_compute_disk_iam_binding.this
}
```

[top](#index)