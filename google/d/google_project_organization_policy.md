# google_project_organization_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_project_organization_policy" {
  source = "./modules/google/d/google_project_organization_policy"

  # constraint - (required) is a type of string
  constraint = null
  # project - (required) is a type of string
  project = null
}
```

[top](#index)

### Variables

```hcl
variable "constraint" {
  description = "(required) - The name of the Constraint the Policy is configuring, for example, serviceuser.services."
  type        = string
}

variable "project" {
  description = "(required) - The project ID."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "google_project_organization_policy" "this" {
  constraint = var.constraint
  project    = var.project
}
```

[top](#index)

### Outputs

```hcl
output "boolean_policy" {
  description = "returns a list of object"
  value       = data.google_project_organization_policy.this.boolean_policy
}

output "etag" {
  description = "returns a string"
  value       = data.google_project_organization_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = data.google_project_organization_policy.this.id
}

output "list_policy" {
  description = "returns a list of object"
  value       = data.google_project_organization_policy.this.list_policy
}

output "restore_policy" {
  description = "returns a list of object"
  value       = data.google_project_organization_policy.this.restore_policy
}

output "update_time" {
  description = "returns a string"
  value       = data.google_project_organization_policy.this.update_time
}

output "version" {
  description = "returns a number"
  value       = data.google_project_organization_policy.this.version
}

output "this" {
  value = google_project_organization_policy.this
}
```

[top](#index)