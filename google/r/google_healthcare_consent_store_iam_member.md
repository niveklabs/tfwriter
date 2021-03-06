# google_healthcare_consent_store_iam_member

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
module "google_healthcare_consent_store_iam_member" {
  source = "./modules/google/r/google_healthcare_consent_store_iam_member"

  # consent_store_id - (required) is a type of string
  consent_store_id = null
  # dataset - (required) is a type of string
  dataset = null
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
variable "consent_store_id" {
  description = "(required)"
  type        = string
}

variable "dataset" {
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
resource "google_healthcare_consent_store_iam_member" "this" {
  # consent_store_id - (required) is a type of string
  consent_store_id = var.consent_store_id
  # dataset - (required) is a type of string
  dataset = var.dataset
  # member - (required) is a type of string
  member = var.member
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
  value       = google_healthcare_consent_store_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_healthcare_consent_store_iam_member.this.id
}

output "this" {
  value = google_healthcare_consent_store_iam_member.this
}
```

[top](#index)