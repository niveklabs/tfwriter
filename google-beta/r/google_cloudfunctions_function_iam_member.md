# google_cloudfunctions_function_iam_member

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
module "google_cloudfunctions_function_iam_member" {
  source = "./modules/google-beta/r/google_cloudfunctions_function_iam_member"

  # cloud_function - (required) is a type of string
  cloud_function = null
  # member - (required) is a type of string
  member = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
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
variable "cloud_function" {
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

variable "region" {
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
resource "google_cloudfunctions_function_iam_member" "this" {
  cloud_function = var.cloud_function
  member         = var.member
  project        = var.project
  region         = var.region
  role           = var.role

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
  value       = google_cloudfunctions_function_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_cloudfunctions_function_iam_member.this.id
}

output "project" {
  description = "returns a string"
  value       = google_cloudfunctions_function_iam_member.this.project
}

output "region" {
  description = "returns a string"
  value       = google_cloudfunctions_function_iam_member.this.region
}

output "this" {
  value = google_cloudfunctions_function_iam_member.this
}
```

[top](#index)