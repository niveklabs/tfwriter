# google_project_iam_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_project_iam_policy" {
  source = "./modules/google/r/google_project_iam_policy"

  # policy_data - (required) is a type of string
  policy_data = null
  # project - (required) is a type of string
  project = null
}
```

[top](#index)

### Variables

```hcl
variable "policy_data" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "google_project_iam_policy" "this" {
  policy_data = var.policy_data
  project     = var.project
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = google_project_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_project_iam_policy.this.id
}

output "this" {
  value = google_project_iam_policy.this
}
```

[top](#index)