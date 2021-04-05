# google_project_iam_custom_role

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
module "google_project_iam_custom_role" {
  source = "./modules/google/r/google_project_iam_custom_role"

  # description - (optional) is a type of string
  description = null
  # permissions - (required) is a type of set of string
  permissions = []
  # project - (optional) is a type of string
  project = null
  # role_id - (required) is a type of string
  role_id = null
  # stage - (optional) is a type of string
  stage = null
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A human-readable description for the role."
  type        = string
  default     = null
}

variable "permissions" {
  description = "(required) - The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified."
  type        = set(string)
}

variable "project" {
  description = "(optional) - The project that the service account will be created in. Defaults to the provider project configuration."
  type        = string
  default     = null
}

variable "role_id" {
  description = "(required) - The camel case role id to use for this role. Cannot contain - characters."
  type        = string
}

variable "stage" {
  description = "(optional) - The current launch stage of the role. Defaults to GA."
  type        = string
  default     = null
}

variable "title" {
  description = "(required) - A human-readable title for the role."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_project_iam_custom_role" "this" {
  description = var.description
  permissions = var.permissions
  project     = var.project
  role_id     = var.role_id
  stage       = var.stage
  title       = var.title
}
```

[top](#index)

### Outputs

```terraform
output "deleted" {
  description = "returns a bool"
  value       = google_project_iam_custom_role.this.deleted
}

output "id" {
  description = "returns a string"
  value       = google_project_iam_custom_role.this.id
}

output "name" {
  description = "returns a string"
  value       = google_project_iam_custom_role.this.name
}

output "project" {
  description = "returns a string"
  value       = google_project_iam_custom_role.this.project
}

output "this" {
  value = google_project_iam_custom_role.this
}
```

[top](#index)