# google_iam_testable_permissions

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_iam_testable_permissions" {
  source = "./modules/google-beta/d/google_iam_testable_permissions"

  # custom_support_level - (optional) is a type of string
  custom_support_level = null
  # full_resource_name - (required) is a type of string
  full_resource_name = null
  # stages - (optional) is a type of list of string
  stages = []
}
```

[top](#index)

### Variables

```terraform
variable "custom_support_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "full_resource_name" {
  description = "(required)"
  type        = string
}

variable "stages" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_iam_testable_permissions" "this" {
  # custom_support_level - (optional) is a type of string
  custom_support_level = var.custom_support_level
  # full_resource_name - (required) is a type of string
  full_resource_name = var.full_resource_name
  # stages - (optional) is a type of list of string
  stages = var.stages
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_iam_testable_permissions.this.id
}

output "permissions" {
  description = "returns a list of object"
  value       = data.google_iam_testable_permissions.this.permissions
}

output "this" {
  value = google_iam_testable_permissions.this
}
```

[top](#index)