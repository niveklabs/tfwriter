# google_pubsub_subscription_iam_policy

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
module "google_pubsub_subscription_iam_policy" {
  source = "./modules/google/r/google_pubsub_subscription_iam_policy"

  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
  # subscription - (required) is a type of string
  subscription = null
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

variable "subscription" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_pubsub_subscription_iam_policy" "this" {
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
  # project - (optional) is a type of string
  project = var.project
  # subscription - (required) is a type of string
  subscription = var.subscription
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_pubsub_subscription_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_pubsub_subscription_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_pubsub_subscription_iam_policy.this.project
}

output "this" {
  value = google_pubsub_subscription_iam_policy.this
}
```

[top](#index)