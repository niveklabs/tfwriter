# google_binary_authorization_attestor_iam_policy

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
module "google_binary_authorization_attestor_iam_policy" {
  source = "./modules/google-beta/r/google_binary_authorization_attestor_iam_policy"

  # attestor - (required) is a type of string
  attestor = null
  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "attestor" {
  description = "(required)"
  type        = string
}

variable "policy_data" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_binary_authorization_attestor_iam_policy" "this" {
  attestor    = var.attestor
  policy_data = var.policy_data
  project     = var.project
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_binary_authorization_attestor_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_binary_authorization_attestor_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_binary_authorization_attestor_iam_policy.this.project
}

output "this" {
  value = google_binary_authorization_attestor_iam_policy.this
}
```

[top](#index)