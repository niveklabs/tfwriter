# google_bigquery_dataset_iam_member

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_bigquery_dataset_iam_member" {
  source = "./modules/google-beta/r/google_bigquery_dataset_iam_member"

  # dataset_id - (required) is a type of string
  dataset_id = null
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
variable "dataset_id" {
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
resource "google_bigquery_dataset_iam_member" "this" {
  # dataset_id - (required) is a type of string
  dataset_id = var.dataset_id
  # member - (required) is a type of string
  member = var.member
  # project - (optional) is a type of string
  project = var.project
  # role - (required) is a type of string
  role = var.role

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
  value       = google_bigquery_dataset_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_bigquery_dataset_iam_member.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_dataset_iam_member.this.project
}

output "this" {
  value = google_bigquery_dataset_iam_member.this
}
```

[top](#index)