# google_iap_app_engine_service_iam_binding

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
module "google_iap_app_engine_service_iam_binding" {
  source = "./modules/google-beta/r/google_iap_app_engine_service_iam_binding"

  # app_id - (required) is a type of string
  app_id = null
  # members - (required) is a type of set of string
  members = []
  # project - (optional) is a type of string
  project = null
  # role - (required) is a type of string
  role = null
  # service - (required) is a type of string
  service = null

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
variable "app_id" {
  description = "(required)"
  type        = string
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

variable "role" {
  description = "(required)"
  type        = string
}

variable "service" {
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
resource "google_iap_app_engine_service_iam_binding" "this" {
  app_id  = var.app_id
  members = var.members
  project = var.project
  role    = var.role
  service = var.service

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
  value       = google_iap_app_engine_service_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_iap_app_engine_service_iam_binding.this.id
}

output "project" {
  description = "returns a string"
  value       = google_iap_app_engine_service_iam_binding.this.project
}

output "this" {
  value = google_iap_app_engine_service_iam_binding.this
}
```

[top](#index)