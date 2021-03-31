# google_folder_iam_member

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_folder_iam_member" {
  source = "./modules/google/r/google_folder_iam_member"

  # folder - (required) is a type of string
  folder = null
  # member - (required) is a type of string
  member = null
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
variable "folder" {
  description = "(required)"
  type        = string
}

variable "member" {
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
resource "google_folder_iam_member" "this" {
  folder = var.folder
  member = var.member
  role   = var.role

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
  value       = google_folder_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_folder_iam_member.this.id
}

output "this" {
  value = google_folder_iam_member.this
}
```

[top](#index)