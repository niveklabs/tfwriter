# google_iap_web_type_app_engine_iam_member

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
module "google_iap_web_type_app_engine_iam_member" {
  source = "./modules/google-beta/r/google_iap_web_type_app_engine_iam_member"

  # app_id - (required) is a type of string
  app_id = null
  # member - (required) is a type of string
  member = null
  # project - (optional) is a type of string
  project = null
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
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "member" {
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
resource "google_iap_web_type_app_engine_iam_member" "this" {
  app_id  = var.app_id
  member  = var.member
  project = var.project
  role    = var.role

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
  value       = google_iap_web_type_app_engine_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_iap_web_type_app_engine_iam_member.this.id
}

output "project" {
  description = "returns a string"
  value       = google_iap_web_type_app_engine_iam_member.this.project
}

output "this" {
  value = google_iap_web_type_app_engine_iam_member.this
}
```

[top](#index)