# google_compute_machine_image_iam_policy

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_machine_image_iam_policy" {
  source = "./modules/google-beta/r/google_compute_machine_image_iam_policy"

  # machine_image - (required) is a type of string
  machine_image = null
  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "machine_image" {
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
resource "google_compute_machine_image_iam_policy" "this" {
  machine_image = var.machine_image
  policy_data   = var.policy_data
  project       = var.project
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_compute_machine_image_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_compute_machine_image_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_machine_image_iam_policy.this.project
}

output "this" {
  value = google_compute_machine_image_iam_policy.this
}
```

[top](#index)