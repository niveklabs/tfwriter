# google_folder_iam_policy

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
module "google_folder_iam_policy" {
  source = "./modules/google-beta/r/google_folder_iam_policy"

  # folder - (required) is a type of string
  folder = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "folder" {
  description = "(required)"
  type        = string
}

variable "policy_data" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_folder_iam_policy" "this" {
  # folder - (required) is a type of string
  folder = var.folder
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_folder_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_folder_iam_policy.this.id
}

output "this" {
  value = google_folder_iam_policy.this
}
```

[top](#index)