# google_sourcerepo_repository_iam_policy

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
module "google_sourcerepo_repository_iam_policy" {
  source = "./modules/google-beta/r/google_sourcerepo_repository_iam_policy"

  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_data" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "google_sourcerepo_repository_iam_policy" "this" {
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
  # project - (optional) is a type of string
  project = var.project
  # repository - (required) is a type of string
  repository = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_sourcerepo_repository_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_sourcerepo_repository_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_sourcerepo_repository_iam_policy.this.project
}

output "this" {
  value = google_sourcerepo_repository_iam_policy.this
}
```

[top](#index)