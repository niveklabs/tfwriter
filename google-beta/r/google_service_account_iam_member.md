# google_service_account_iam_member

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
module "google_service_account_iam_member" {
  source = "./modules/google-beta/r/google_service_account_iam_member"

  # member - (required) is a type of string
  member = null
  # role - (required) is a type of string
  role = null
  # service_account_id - (required) is a type of string
  service_account_id = null

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
variable "member" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "service_account_id" {
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
resource "google_service_account_iam_member" "this" {
  # member - (required) is a type of string
  member = var.member
  # role - (required) is a type of string
  role = var.role
  # service_account_id - (required) is a type of string
  service_account_id = var.service_account_id

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
  value       = google_service_account_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_service_account_iam_member.this.id
}

output "this" {
  value = google_service_account_iam_member.this
}
```

[top](#index)