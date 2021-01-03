# google_project

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_project" {
  source = "./modules/google-beta/d/google_project"

  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(optional) - The project ID. Changing this forces a new project to be created."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_project" "this" {
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "auto_create_network" {
  description = "returns a bool"
  value       = data.google_project.this.auto_create_network
}

output "billing_account" {
  description = "returns a string"
  value       = data.google_project.this.billing_account
}

output "folder_id" {
  description = "returns a string"
  value       = data.google_project.this.folder_id
}

output "id" {
  description = "returns a string"
  value       = data.google_project.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_project.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.google_project.this.name
}

output "number" {
  description = "returns a string"
  value       = data.google_project.this.number
}

output "org_id" {
  description = "returns a string"
  value       = data.google_project.this.org_id
}

output "skip_delete" {
  description = "returns a bool"
  value       = data.google_project.this.skip_delete
}

output "this" {
  value = google_project.this
}
```

[top](#index)