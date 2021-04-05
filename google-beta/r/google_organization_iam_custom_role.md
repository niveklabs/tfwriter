# google_organization_iam_custom_role

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
module "google_organization_iam_custom_role" {
  source = "./modules/google-beta/r/google_organization_iam_custom_role"

  # description - (optional) is a type of string
  description = null
  # org_id - (required) is a type of string
  org_id = null
  # permissions - (required) is a type of set of string
  permissions = []
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

variable "org_id" {
  description = "(required) - The numeric ID of the organization in which you want to create a custom role."
  type        = string
}

variable "permissions" {
  description = "(required) - The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified."
  type        = set(string)
}

variable "role_id" {
  description = "(required) - The role id to use for this role."
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
resource "google_organization_iam_custom_role" "this" {
  description = var.description
  org_id      = var.org_id
  permissions = var.permissions
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
  value       = google_organization_iam_custom_role.this.deleted
}

output "id" {
  description = "returns a string"
  value       = google_organization_iam_custom_role.this.id
}

output "name" {
  description = "returns a string"
  value       = google_organization_iam_custom_role.this.name
}

output "this" {
  value = google_organization_iam_custom_role.this
}
```

[top](#index)