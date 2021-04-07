# google_service_directory_service_iam_policy

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
module "google_service_directory_service_iam_policy" {
  source = "./modules/google-beta/r/google_service_directory_service_iam_policy"

  # name - (required) is a type of string
  name = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
resource "google_service_directory_service_iam_policy" "this" {
  # name - (required) is a type of string
  name = var.name
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_service_directory_service_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_service_directory_service_iam_policy.this.id
}

output "this" {
  value = google_service_directory_service_iam_policy.this
}
```

[top](#index)